---
title: "Using the BioHPC Computer Cluster"
teaching: 5
exercises: 20
questions:
- "How can I cement my understanding of Git's functions?"
objectives:
- "rephrase Git commands using everyday language"
- "demonstrate Git's functions by drawing or sketching" 
keypoints:
- "the language of Git can be confusing and intimidating"
- "rephrasing commands and drawing concepts can clarify Git's workflow"
---
### Introduction to the compute cluster

Our compute cluster is called Nucleus, and has 574 nodes right now. Nucleus is a heterogeneous cluster, with a variety of different nodes with different specifications. Nodes are available with 32GB, 128GB, 256GB, and even 384GB of memory and several dozen computational threads, as well as many additional nodes with modern GPU cards.The cluster is running RedHat Enterprise Linux 7.6, and uses the SLURM job scheduling software.  Those familiar with the TACC Stampede supercomputer at UT Austin will recognize similarities between our setup and theirs.

Generally, to run programs on Nucleus you must interact with the SLURM job scheduler and understand how to use software modules. The job scheduler allocates time on the cluster to users, queueing their jobs and running them when compute nodes are available. Jobs can be submitted to the scheduler manually via the command line, or more easily using the online submission tool. Tasks which are more easily performed through an ordinary desktop environment can be done in the context of a Web Visualization job, allowing you to access a BioHPC desktop environment from your local workstation, Windows PC, or Mac.

### The modules system for software

BioHPC serves a variety of users with different and sometimes conflicting computational needs. Different software, libraries, and even different versions of each package might be necessary for performing your work. We use a system of ‘modules’ to provide a wide range of packages. On the cluster or clients and workstations, you can load modules of software that you need. If you need additional software, or updated versions of existing software then please email us. If you are trying things out, and know how to, you can also install software into your home directory for your sole use.

Here’s an example of using software modules where we want to run the 'cufflinks' RNA-Seq analysis tool. From a command line on the compute cluster or a workstation we can run module list to see software modules currently in-use in our current session. If we try to run the cufflinks command it fails, because the relevant module is not loaded. To run software the system must know the path of the program, and often the location of libraries and configuration. Each module provides this information for a particular software package.

We can search for a cufflinks module with module avail cufflinks, and then load it into our session with module load cufflinks or module load cufflinks/2.1.1 if we want version 2.1.1 specifically. Now the output of module list shows the cufflinks modules, as well as boost – a library which cufflinks depends on. We can now run the cufflinks command directly to use the software, as below:

### Module Commands

To use BioHPC software modules effectively, familiarize yourself with the following commands, which load, unload, list, search for, and display help about modules. Remember that you can contact biohpc-help@utsouthwestern.edu if you are unsure about a module, which version of a module to use, or if you need additional software setup.

~~~
$ pwd
~~~
{: .language-bash}

~~~
Currently Loaded Modulefiles:
  1) shared              2) slurm/16.05.8
~~~
{: .output}

Here,
the computer's response is list of default modules loaded

Show loaded modules

module avail\
Show available modules

module load <module name>\
Load a module, setting paths and environment in the current session

module unload <module name>\
Unload a module, removing it from the current session.

module help <module name>\
Help notes for a module

module –H\
Help for the module command

You could also check the availabe module through portal - software - module browser.
  
### Submitting a compute job via the portal

Once you have transferred data to BioHPC storage, the easiest way to submit a compute job is to use the Web Job Submission tool, which can be accessed from the BioHPC portal Cloud Services menu. This tool allows you to setup a job using a simple web form, automatically creating and submitting the job script to the SLURM scheduler on the cluster. Work through the form, filling in the fields according to the information below:
  
              
* **Job Name**This is a name for your job, which will be visible in the output of the squeue command, and on the public job list shown on the BioHPC Portal. Use a short but descriptive name without spaces or special characters to identify your job.
* **Modules**	When running a job, you must load any modules that provide software packages you require. If you are going to run a MATLAB script, you must load a MATLAB module. Click the Select Modules button to access the module list. You can select any combination of modules with checkboxes. Note, however that some combinations don't make sense (e.g. 2 versions of the same package)  and may cause an error on submission.
* **STDOUT** file	Any output your commands would normally print to the screen or console will be directed to this file when your job is run on the cluster. You will find the file within your home directory, under the portal_jobs subdirectory. You can use the code '%j' to include the numeric job ID in the filename.
* **STDERR** file	Any errors your commands would normally print to the screen will be directed to this file when your job is run on the cluster. You will find the file within your home directory, under the portal_jobs subdirectory. You can use the code '%j' to include the numeric job ID in the filename.
* **Partition/Queue**	The Nucleus cluster contains nodes with different amounts of RAM, and some with GPU cards. The cluster is organized into partitions separating these nodes. You can choose either a specific RAM partition, the GPU partition if you need a GPU card, or you can use the super partition. The super partition is an aggregate partition containing all 32, 128, 256 and 384GB nodes which can be used when it's not important that your job runs on any single specific type of node.
* **Number of Nodes**	The number of nodes required for your job. Programs do not automatically run on more than one node - they must use a parallel framework such as MPI to spread work over multiple nodes. Please review the SLURM training before attempting to run jobs across multiple nodes.
* **Memory Limit (GB**)	Specifies the amount of RAM your job needs. The options will depend on the partition selected. Choose the lowest amount required in order that your job can be allocated on the widest range of nodes, reducing wait times.
* **Email me**	The SLURM scheduler can send you an email when your job starts running, finishes etc. You can turn these emails off if you wish.
* **Time Limit**	Try to estimate the amount of time your job needs, add a margin of safety and enter that time here. The scheduler relies on job time limits to efficiently fit smaller jobs in between larger ones. Jobs with shorter time limits will generally be scheduled more quickly. Beware - this is a hard limit. If your job take longer than the limit entered it will be killed by the scheduler.
* **Job Command**	The actual commands to run, such as 'matlab -nodisplay < hello.m' to run a matlab script, are entered in this section. You can have one or more command groups, each containing one or more commands. All of the commands in a group will be run at the same time, in parallel. The groups themselves run sequentially. Everything in the first group must finish before the second group begins. By default there is a single command in the first group, hostname.  This simply prints the name of the compute node your job runs on. You can replace it with a real command, or add another command group for your own commands.
  
 Below the web form you will see the SLURM sbatch script that is being created from your choices. It is updated whenever you make a change in the form. The script contains comments beginning with #, and parameters for the scheduler beginning with #SBATCH. Setting up jobs using the web form and then reviewing the script that is created is a good way to learn the basics of SLURM job scripts so that you can write your own. Note that you can even edit the script before you submit the job, but a script that as been edited cannot be further modified using the web form.
  
 When you are happy with the settings and commands for your job, you can submit it using the button at the bottom of the page, below the script. If the format is good and the settings are valid, the Portal will report that the job has been submitted and supply a Job ID. If there is a problem you may receive an error message from sbatch, which the portal will display. You can email with any questions or problems you have submitting jobs.
  
 ### Connecting to an interactive GUI visualization session
  
BioHPC allows interactive use of cluster nodes, for visualization debugging and running interactive software, through the portal's Web Visualization service. Using this interface, you can run a Linux desktop session on a cluster node (WebGUI), on a GPU node with 3D OpenGL acceleration (WebGPU), or start a powerful Windows 7 virtual machine with 3D acceleration (WebWindows). To start a session and connect to it, use the Web Visualization link in the Cloud Services menu of the Portal:
                                                                                  
The page that is displayed lists the connection information for any currently running visualization sessions you may be running. At the bottom is a form allowing you to start a new session. Choose the type of session you need and click the submit button to queue the visualization job on the cluster. All visualization jobs are limited to 20 hours. Visualization jobs are like any other SLURM job and are dependent on node availability so it can take some time for them to start when the cluster queue is busy. Note that the 20 hour time limit only applies once your visualization job is actually running. Once a session has started you will see VNC connection details for your session, and a link to connect directly from your web browser. The screenshot below shows MATLAB running in a WebGPU session with a connection made from the web browser:
 
The web browser connections is convenient, but a smoother and higher resolution experience is possible by connecting using a VNC client, particularly if you are using a wired network connection on campus. Connection details are displayed for each running session. If you are not using a BioHPC client or workstation you can download the TurboVNC client on our Software page. TurboVNC is the recommended VNC client for best performance and compatibility with our sessions. To resize the Turbo VNC client, increase the resolution of the client through System->Preferences->Display menu to increase the display size of the client on the host machines. Higher resolution can cause a slower or higher-latency experience.

### Command line access via the portal and SSH
  
If you are comfortable using the Linux command line, or want to learn, you can login to our systems using the Secure Shell (SSH) to the nucleus.biohpc.swmed.edu cluster head node, also known as nucleus005. The head node of the cluster allows users to login, manipulate and edit files, compile code and submit jobs. It should not be used to run analyses, as this will affect the response for others who are using the system. Software and analyses which consume excessive RAM or CPU time on shared nodes are subject to being terminated without warning.

The easiest way to login to the cluster is to use the Cloud Services - Nucleus Web Terminal of the portal website. This provides a command line interface inside your web browser. You will need to enter your BioHPC password when the connection is made. Note that if you close your browser, or browse to a different page, your connection will close.
  
To login using a stand-alone SSH client, please connect to nucleus.biohpc.swmed.edu using your biohpc username and password.

If you are using a Mac or Linux computer, you can use the ssh command in a terminal window - ssh username@nucleus.biohpc.swmed.edu

If you are using a Windows PC you will need to download an SSH client program. We recommend , which is available via a link on the portal Software section.
  
### Useful Linux Commands
  
The following commands are useful when working with Linux on BioHPC. See also the material from our Linux command line & scripting training session.

quota –ugs\
Show home directory and project directory quota and usage

panfs_quota -G /work\
Show work directory quota and usage

du –sh <directory>\
Show size of a specific directory and it’s contents

squeue\
Show cluster job information

sinfo\
Show cluster node status

sbatch myscript.sh\
Submit a cluster batch job using a script file

cat filename\
Display a file on the screen

less filename\
Displays a file so that you can scroll up and down. ‘q’ or ctrl-c quits

vi or vim\
Powerful text editors, with a cryptic set of commands! See

nano\
Simpler, easier to use! See

### Using the SLURM Job Scheduler
  
Earlier in this document, we described how to submit a job using the web job submission service on the BioHPC portal. You can also work with the cluster's SLURM job scheduler from the command line. If you are familiar with another job scheduler (e.g. PBS, SGE), SLURM is similar but with different names for the common commands.

A comprehensive training session on using the SLURM job scheduler is given every 3 months. Please check the BioHPC training calendar and the materials from past sessions for more information.
  
**squeue - view the job queue** - From any biohpc system you can run the squeue command to display a list of jobs currently being managed by the scheduler. The job status is shown as a 1-2 letter code, and times are in Days-Hours:Mins:Seconds format:

The list of jobs on the cluster can be long at times. To see only your own jobs use the **-u <username>** option, e.g. **squeue -u dtrudgian**
  
**sbatch - submit a job** - If you are comfortable writing SLURM job scripts for your jobs you can submit them to the cluster using the sbatch command. In the sample below the script myjob.sh was created using the vi editor, then submitted using **sbatch myjob.sh**. The output of the sbatch command is a numeric job ID if successful, or any error message if there are problems with your job script. Once you have submitted a job you can see it in the cluster queue with the **squeue** command. In the example, the job is waiting to run with the reason given as (RESOURCES) as the scheduler is waiting for a node to become available:
 
When  a node became available the job was executed successfully, and output messages written into the file specified in the job script. In this case the file was named <em>job_26948.out</em> and we can view it's content with the **cat** command

**scancel - cancelling a submitted job** - If you make a mistake when submitting a job, please cancel it so that it does not occupy time on the cluster. The **scancel** command takes a job ID as it's only argument. In the example below we use the comand **scancel 26953** to stop our job running. We can check that it was cancelled correctly, by examining the output of squeue - the job is no longer in the cluster queue. If you don't remember the job ID for a job you need to cancel check the output of **squeue -u <username>** which will list the details of all of your current jobs.

### Next Steps

Now that you have worked through this introduction to BioHPC you should experiment with our systems! Make sure you can successfully login to the Portal, use the web based job submission and connect to a web visualization session.

We offer training sessions on our cloud storage system, the SLURM scheduler, and a variety of other topics relevant to using BioHPC Please check the training calendar and make a note of any sessions that are applicable to your work.

If you have any questions, comments, or sugesstions please contact us via  or use the 'Comment on this page' link above the menu bar.
  

  
