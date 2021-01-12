---
layout: default
---

# Setting up a JupyterHub for Teaching Workshops on AWS

JupyterHub is a great way to run basic Python coding workshops. People can come in and start coding with zero setup ahead of time on their own machines--all they need is a web browser. This page describes my method of setting up a JupyterHub on Amazon Web Services, adding workshop data to the JupyterHub, and distributing lessons to the participants as Jupyter Notebooks via GitHub.
![Pandas Logo][JupyterHub]  

***
Phil White, , Earth, Environment & Geospatial Librarian, University of Colorado Boulder  
[philip.white@colorado.edu](mailto:philip.white@colorado.edu)

***
***
My Stack:
![my stack][myStack]

***
Prerequisites:
- [Amazon Web Services](https://aws.amazon.com/) account
- [GitHub](https://github.com/) account & [basic understanding of GitHub](https://towardsdatascience.com/getting-started-with-git-and-github-6fcd0f2d4ac6)
- Some command line knowledge
- Some Python programming experience
***

## Part 1: Deploying JupyterHub

The easiest and probably most appropriate deployment of JupyterHub for workshops and smaller classes is [The Littlest Jupyter Hub (TLJH)](http://tljh.jupyter.org/en/latest/). TLJH is ideal for 100 users or less.

[Install TLJH on Amazon Web Services](http://tljh.jupyter.org/en/latest/install/amazon.html). I can do no better than TLJH's own very clear instructions. This is straightforward and can be accomplished in literally just a few minutes. I was successful in launching my own JupyterHub on an EC2 instance on the first try, and I had zero experience doing something like this at that time.

Be sure to save your key pair in a safe place.

I have only deployed TLJH on Amazon Web Services, but there are great instructions for [installing TLJH on other platforms](http://tljh.jupyter.org/en/latest/install/index.html) as well.

### Some things to be aware of:
- You'll be deploying TLJH on an EC2 instance.
- You can set up your Hub on EC2's free tier initially, which I recommend...
- BUT you will want to upgrade memory and processing power when you're actually running the workshop. See Part 4 below.
- AND a server costs money! But, with AWS, it only costs money while you're running it. And you may qualify for the free tier for one year. So, your initial installation will be set up with less processing power and less memory, qualifying for the free tier (for one year). This will be nice while you're learning your way around.
- When you're not using it, I recommend getting into the habit of shutting off. When/if you upgrade, you'll want to shut it off when not running so as to avoid running up your bill unnecessarily.
- All that said, AWS is very affordable. Here is a nice [breakdown of the pricing structure](https://www.ec2instances.info/).
- Per the instructions, I am running a t2 instance, because my initial set up with t2micro was free for the first year. I upgrade/downgrade only when necessary and keep it turned off when not using.
- Don't forget to turn off when not using! Otherwise you'll have a surprise bill (As a point of reference, I accidentally left a different EC2 instance running for about 2 weeks amounting to a monthly bill over $20). But this was a high powered instance. Most are pennies per hour.

## Part 2: Set up the JupyterHub  

In AWS, under Instances, you can launch/shutdown your instance (Actions>Instance State>Start). Then, your JupyterHub's url will be visible as IPv4 Public IP. Mine looks like this:
![Hub Address][hubAddress]

Copy and paste the URL into a new browser tab and visit your JupyterHub. Log-in with the username and password you set up previously (or set your password on first log-in).


If you've used Jupyter Notebooks before, this will look familiar. The only difference is that with Hub it's served on the web instead of serving from  your local computer.


### Add all necessary Python packages

You'll need to add all of the Python packages that you'll be using in the workshop. The default installation comes with most everything you'll need, but likely you'll need to add a few.

Open up a terminal within JupyterHub:
![Terminal Launch][termLaunch]

You could SSH into your server using the key pair and an SSH client like PuTTY or something similar. But, it's easy and just as effective to use the terminal within JupyterHub.

As noted in the installation instructions, you'll need to use sudo commands along with your typical package manager (like pip or conda) to install the packages you need, like so:

```
sudo -E pip install geopandas
```
OR
```
sudo -E conda install geopandas
```

In my most recent GeoPandas workshop, I installed the following packages using these commands:
```
sudo -E pip install pandas
sudo -E pip install geopandas
sudo -E pip install matplotlib
sudo -E pip install descartes
sudo -E conda install rtree
```

Following my methods, you will also need to install Git on your instance:
```
sudo apt install git
```

### Set up your data directory  

There are [different methods of both adding data to your JupyterHub](http://tljh.jupyter.org/en/latest/howto/content/add-data.html) and [distributing data to your users](http://tljh.jupyter.org/en/latest/howto/content/share-data.html#howto-content-share-data). One would be to store data on GitHub and have each individual download it and add it themselves. Another would be to add it to each user's folder. However, there are downsides to those methods: First, having participants add it themselves is one more thing that could fail and that's what we're trying to avoid here, right? Adding it to each person's user directory would require extra planning and hassle on your behalf.

<em>My preferred method</em> is to add all workshop data from a GitHub repository to a read-only folder that all users have access to. Then, during the workshop, they can all read the data and perform tasks without any problems because all of their individual operations take place in RAM; any output files can be written to their own directory.*

A bonus is that by storing the data on GitHub, users can access it later when/if your server is inactive.

Another bonus is that this takes up much less space on your server instance. Instead of duplicating the workshop data on each users' space on the JupyterHub, they will each access the same folder.

In the end, this solution saves you time <em>AND</em> money.

Here are the steps:

1. Create a GitHub repository and add all of the workshop data to the repository. If you're new to GitHub, this is easy. Here is a [GitHub Guide](https://guides.github.com/activities/hello-world/) and [how to upload files](https://help.github.com/en/github/managing-files-in-a-repository/adding-a-file-to-a-repository).

2. In your JupyterHub's terminal, you'll first need to change directory back to the root directory. This should do it:
```
cd ../../
```
The working directory will now be jupyter-your_user_name@ip-your_ip_address://. An ```ls``` command should show you the following directories:
![root ls][rootls]
For future reference, each individual's workspace, including your own, is located in home.

3. Next, create a new folder in your data directory named 'workshopdata'. The data directory is located at //srv//data. From your root directory, use the following command:
```
sudo mkdir -p /srv/data/workshopdata
```

4. Next, add an alias 'workshopdata' directory to all users' folders. Essentially, this makes a read-only workshopdata folder in each user's directory. All new users will have a workshopdata folder when they log into their space on the JupyterHub. First, change directory to the etc//skel folder:
```
cd /etc/skel
```
Then, create the alias directory:
```
sudo ln -s /srv/data/workshopdata workshopdata
```

5. Now, navigate back to your 'workshopdata' folder. First, back out to your root directory:
```
cd ../../
```
Then:
```
cd /srv/data/workshopdata
```

6. Now, you will make your 'workshopdata' folder a Git repository:
```
sudo git init
```

7. Now you will pull all of your workshop data from the GitHub repository you created in step one into this workshopdata directory using Git commands. First, connect to your data repository:
```
sudo git remote add origin https://github.com/your_username/your_data_repo.git
```
Then pull the data:
```
sudo git pull origin master
```
This will add all of your workshop data on GitHub to your JupyterHub's workshopdata directory. If you update your data repository on GitHub later, just use the sudo git pull orgin master command to update your workshopdata directory.

Now, each new user will have a read-only data directory in their space on the JupyterHub.

Note*: Using this method underscores the importance of users being able to both navigate filesystems and change directories using Python commands--important computer-literacy skills for any coder. This means using the Python package 'os'. They'll need to change to their home directories at the beginning of each lesson and access each dataset using the workshopdata/ prefix. [See example here in codeblock 2 and 3](https://outpw.github.io/2.%20Selecting%20%26%20Filtering%20by%20Attributes%3B%20More%20Plotting.html)

### Adding Users to the JupyterHub:
Adding users to the JupyterHub is extremely easy. Your choice is when to add them. You can add users in advance, which is helpful if you know you will have a large workshop. But because it is so easy to do, I typically create the users on the fly as workshop participants walk into the room. I will ask them what they want their username to be and then create it.

To create users, click Control Panel in your JupyterHub, then Admin.

Next click add users, then type in user names separated by a return, like this:
![Add users][addUsers]


## Part 3: Distributing workshop Notebooks

I like to break different lessons up into different notebooks. For my GeoPandas workshop, I provide [five notebooks](https://github.com/outpw/geopandas_notebooks) that the participants work through. The notebooks include prompts for the participants, and they have to type all the code and run it themselves. The markdown functionality in notebooks also let's you ask questions and give the participants some problem solving activities.

To distribute the notebooks, I use [nbgitpuller, following the instructions provided by TLJH](http://tljh.jupyter.org/en/latest/howto/content/nbgitpuller.html#howto-content-nbgitpuller). This requires that you keep your Notebooks in a GitHub repository. This is separate from the repository used to store the workshop data. I usually also provide completed versions of the notebooks in a folder in the same repository. [For example.](https://github.com/outpw/geopandas_notebooks)

nbgitpuller creates a simple link that will pull the notebooks from your GitHub repository and add them to each user's workspace on the JupyterHub. Participants will just need to visit the nbgitpuller link and all the notebooks will be added to their space on the hub. [See my workshop docs](https://outpw.github.io/tutorials/GeoPandas-setup.html) for an example of how this is presented to the workshop attendees.

All you need is the link to your JupyterHub and the pull link to your GitHub repository (which should be something like this: https://github.com/your_user_name/your_repo.git)

You may want to consider creating a shortened [bitly link](https://app.bitly.com/bbt2/) of the nbgitpuller link to share with workshop participants.

An added bonus of this method is that your workshop materials are still available for people to run on their personal computers at a later date.

## Part 4: Upgrading your EC2 instance

### Considerations
If you installed TLJH on a t2.micro instance, you will need to upgrade it prior to the workshop. There are two considerations: memory (RAM) and volume (storage space). This is important because if everyone is running a memory-intensive process at the same time during the workshop it can max out the server's memory and start bouncing people from the JupyterHub. Best avoided.

It is also best to avoid running memory-intensive tasks on large data sets during the workshop. Keep the analysis to smaller data sets to avoid over-taxing your system's memory.

Deciding on how much memory is needed is a function of how much RAM your notebooks use at a given time and how many users are concurrently using it. This is fairly straightforward to estimate. When you're running a notebook on JupyterHub, it informs you in the top right how much RAM is being used at that moment:
![Notebook Memory][notebookMem]

I add up the total amount of RAM it takes to run all of the workshop notebooks at the same time, then multiply that by the maximum amount of possible concurrent users. If your participants register ahead of time, this should be easy to figure out. In my experience, t2.xlarge has worked great, but you could probably get by with t2.large instead (or perhaps even less). I usually instruct my participants to close and halt their notebooks when finished so other notebooks aren't running needlessly and taking up valuable memory. [You can view all of the instance options & pricing here](https://www.ec2instances.info/). You can also view all instance types in your EC2 Dashboard under Instance Types.

Volume is a question of how much space the workshop data and notebooks take up on your server instance. It is advantageous to place all workshop data in a read-only folder to avoid unnecessary duplication. This way your server space is limited to just one copy of the workshop data, each participant's notebooks, and whatever other data/notebooks you've used in your admin account while planning/testing the workshop. Estimating how much volume is required is simple. Multiply the total size of all notebooks times total concurrent users, then add the sum of the size of the workshop data as well as the sum of the size of all output data the participants will generate.

### Start by upgrading your EC2 instance:
This part is easy.
1. After logging into AWS, navigate to the AWS Management Console and click EC2. On your EC2 Dashboard, click Instances to view your instance.  

2. Shut down your instance if it is running by clicking Action > Instance State > Start/Stop:  
![Stop Instance][instanceStop]

3. Go to Actions > Instance Settings > Change Instance Type  
![Instance Type][instanceType]

4. Choose an appropriate instance:  
![Choose Type][instanceChoose]

### Expand your server's volume:

1. After logging into AWS, navigate to the AWS Management Console and click EC2. On your EC2 Dashboard, select Volumes under Elastic Block Store:
![EBS Volume][EBSvolume]

2. View your server's volume under Size. Yours is likely 2,4, or 8 GiB. Mine is 16:  
![Volume Size][volSize]

3. Click Actions > Modify Volume:  
![Modify Volume][modVol]

4. Change the size to an appropriate volume. 8 is probably okay. I chose 16 just to be safe. Then click Modify.
![Modify Volume2][modVol2]

5. Next, <em>and this is important</em>, you have to tell your server you to expand to its new size. [Refer to the directions for extending a t2 instance here](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/recognize-expanded-volume-linux.html). You will use your JupyterHub terminal and the ```sudo growpart``` commands as demonstrated under the Extending a Partition > T2 Instance example. You can use the ```lsblk``` command to check your volume before and after. Use the ```df``` command to check how much space is currently used.

### Final Notes

- This is an awesome way to run a workshop. Because I take the time to prepare this way, I have never ran into technical issues and problems during the workshop. Each time I teach a workshop using this setup, participants praise the smoothness of the workshop. Everything just works. Instead of spending time fixing people's tech problems, I spend the whole class time teaching. If they have a problem, likely, they've just made a typo.

- I usually create a second user account for myself set up as a non-admin so I can test everything ahead of time to ensure things work as expected from the participant's perspective. I also use this non-admin user account during the workshop, and delete the notebooks folder so I walk through the exact same steps as each participant, and we all see the same things happening.

- A nice touch is to save your completed notebooks as html and then put them on the internet. This way they can be viewed later by the workshop participants or anyone. I add them to my github.io site then link to them: https://outpw.github.io/3.%20Joins%20%26%20Choropleth%20Plot.html  

- Following the recommendation of my friend Evan Thornberry (GIS Librarian @ UBC), I've recently started using [Jekyll](https://jekyllrb.com/) to host my workshop docs, including this document. I use this along with a github.io site to host workshop documentation that anyone can access anytime. This is all free!

Questions? Email me: [philip.white@colorado.edu](mailto:philip.white@colorado.edu)

[Python]: img/PythonLogo.png
[JupyterHub]: img/hublogo.png
[instanceStop]: img/instanceStartStop.png
[instanceType]: img/instanceType.png
[instanceChoose]: img/instanceChoose.png
[EBSvolume]: img/EBSvol.png
[modVol]: img/modVol.png
[modVol2]: img/modVol2.png
[myStack]: img/hubStack.svg
[hubAddress]: img/hubAddress.png
[termLaunch]: img/termLaunch.png
[rootls]: img/rootls.png
[addUsers]: img/addUsers.png
[notebookMem]: img/notebookMemory.png
[volSize]: img/volSize.png
