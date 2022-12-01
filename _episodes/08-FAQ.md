---
title: "FAQ"
teaching: 15
exercises: 20
questions:
- "Who and what is BioHPC?"
- "What services does BioHPC provide?"
- "How do I register for an account?"
- "When will my account be activated?"
- "What storage is allocated for my account?"
- "Is my data backed up?"
- "How do I contact BioHPC?"

keypoints:
- "GitHub Pages offer an automated way to create a website that is version controlled and accessible for collaboration"
- "Collaborating on a GitHub Pages website uses the same Git/GitHub workflow you learned for collaborating via a GitHub repository"
---

### Who and what is BioHPC?

BioHPC is the high-performance computing resource at UT Southwestern. We provide the hardware, services and assistance necessary for 
UT Southwestern researchers to tackle large computational problems within their research work. BioHPC is different from many HPC centers due 
to the diverse range of users we have. We aim to offer convenient access to our systems using a wide range of cloud services easily used via the web. 
Users can benefit from our large storage systems and powerful compute cluster without needing expertise in Linux and HPC.

BioHPC’s core hardware currently consists of a 574-node compute cluster, and over 20 PB of high-performance storage. Follow the links to our 
to find out more about our systems on this site. Most users will become familiar with the Lamella cloud storage gateway and our compute cluster called Nucleus.

A team of 12 staff from a diversity of backgrounds manages BioHPC systems, collaborates on research projects, and provides general support to users. 
Led by BioHPC director Liqiang Wang, the team has a range of expertise covering bioinformatics work, mathematical simulation, image analysis, software 
development, and hardware support. The best means of contact is by emailing biohpc-help@utsouthwestern.edu.

### What services does BioHPC provide?

* **Storage** – Our high performance storage systems provide user, laboratory, department, and collaboration allocations with fast access from the campus 10Gbps or 1Gbps networks, via web interfaces, drive mounts directly to your workstation, or through FTP transfers.
* **Computing** –  Jobs and interactive GUI sessions can be scheduled on Nucleus, our 574 node cluster. Nucleus features nodes with 32GB, 128GB, 256GB and 384GB of RAM. Additional nodes contain powerful GPUs, including the NVIDIA P4, P40, P100, and V100 cards.
* **Visualization** – Complex 3D visualization tasks can easily be performed on Nucleus' GPU nodes, with smooth and responsive access from your BioHPC workstation, Windows PC, Linux system, or Mac. Sessions can be accessed by VNC connections or within your web browser.
* **Cloud services** – Most of our systems can be accessed via your web browser. Through our portal page, you can submit a job to our SLURM scheduler, access the Nucleus cluster directly, start up and interact with a GUI visualization session, access a powerful web desktop which can share the same workspace across all members of your research group, use our in-house NGS or Galaxy pipelines, store images in our OMERO imagebank, collaborate on and share code with our GitLab repository service, along with many other services.
* **Training** – We offer training sessions at 10:30AM every Wednesday, part of a comprehensive training calendar targeted to the needs of researchers at UTSW. Previous training topics and slides can be found here.
* **Support & Help** – Staff are available to advise and assist you in the effective use of our systems for your research, as well as to help you troubleshoot technical or computational problems.

### How do I register for an account?

Our initial account registration process is automated. Fill out the online registration form and watch for an email to confirm your registration details. Once your account is registered, you will need to attend a mandatory new user introduction session. These take place on the first Wednesday of each month at 10:30AM and are conducted via Microsoft Teams. You will receive training emails once you are registered as a new user.

### When will my account be activated?

Your account will be fully activated for access to our systems after you have attended the introductory training session. Accounts are generally activated in the following 3-4 days. In very busy times when there are a large number of user registrations, you may need to wait a few more days before receiving your activation email.

### How do I contact BioHPC?

You can contact BioHPC staff:

   * **By email to biohpc-help@utsouthwestern.edu**
   * **By telephone at extension 51745**
   * **In person at our office in the E building, 4th floor**

In any case, we strongly prefer that you initially send an email to biohpc-help@utsouthwestern.edu, as this is tracked using a ticket system that allows us to provide a prompt response from the member of staff best equipped to answer your question. Tickets may also be submitted through the BioHPC Portal, but this does not allow you to provide attachments.

### What storage is allocated for my account?

Every BioHPC user received multiple allocations of storage, with different amounts at different locations. The major storage locations on our cluster are known by their path names: home2, project, and work. Standard allocations for each user are:

* **home2 (50 GB/user)** - A quota for a personal home directory at /home2/<username>. This is appropriate for storing private configuration files, scripts, and small programs that you have installed yourself. It should not be used for storing and analyzing large datasets. Exceeding your home2 quota can lead to you being unable to use many BioHPC services.

 * **work (5 TB/user)** – The /work directory is an additional per-user storage area with different hardware than the project space, and is appropriate for 'hot' data which is actively being analyzed, or which is frequently accessed. It should not be used for long-term storage and inactive data should be moved to project space. Each user has a work directory at /work/<department>/<username>. A department shared directory can be found at /work/<department>/shared.

* **project ( 5 TB/group )** - The /project directory is the main storage area on BioHPC, and is appropriate for raw data or data which is not being accessed multiple times a day.  Additional space is available at the request of a lab PI, depending on arrangements with your department. Your lab’s project space can be found at the path /project/<department>/<lab> . Within this space, you are free to organize your data as you would like. Some labs choose to have a folder for each lab member - other labs choose to have folders for each project. All labs have a ‘shared’ folder inside their project space at /project/<department>/<lab>/shared that can be accessed by anyone in the lab group. Another ‘shared’ folder at /project/<department>/shared is accessible by all members of a department.

* **archive ( 5 TB/group )** - The /archive directory is appropriate for 'cold' or infrequently used data, and is not optimized for efficient access. Files stored on /archive consume 2/3 the storage allotment they would in other storage spaces, i.e. a 3GB file will only consume 2GB of your storage allotment. As a result, the 'effective size' of /archive is 7.5 TB. Additional space can be allocated if the request is approved by your department chair.

* **lamella.biohpc.swmed.edu** - 100GB storage on the BioHPC private cloud. Accessible only on campus or while connected to VPN.

* **cloud.biohpc.swmed.edu** - 50GB storage web-interface on our external cloud, can share with researchers outside of our UT Southwestern campus. Please note that this space is not within the main UTSW network, and does not enjoy the same level of security that the other storage spaces do. Under no circumstances is protected data allowed to be placed on the cloud.


### Is my data backed up?
  
It is important that your data be kept safe against accidents and catastrophes. To help ensure your data is kept safe, BioHPC performs backups on a regular basis.

Backups come in two basic forms:

* Mirror backups are a bit-for-bit copy of your data, taken as a single snapshot in time, and are intended to protect against catastrophic loss of data. Mirror backups are overwritten during each backup event, so you will only be able to revert to the point in time that the snapshot was taken
* Incremental backups take an initial single snapshot of your data. After this, each backup event will examine the differences between the old data and the new data and record only the changes. This allows for a more fine-grained rollback, but can consume a large amount of storage if the data has frequent, large changes. **This does not protect against catastrophic data loss.**

  We currently backup data on BioHPC as follows:

* Data stored directly in the lamella.biohpc.swmed.edu system is backed up weekly, creating one mirror copy. This copy does not affect your storage allocation.
* Backup of /home2 is performed twice per week (Mon and Wed), creating two mirror copies representing two points in time. These copies do not affect your storage allocation.
* The files under /work are backed up weekly, creating one mirror copy. This copy does not affect your storage allocation.
* Files under /project are backed up by PI request. Email BioHPC and let us know which directories or files you want to backup, how often the backup should be run, and any other details you feel are relevant. Please note that this backup does consume your /project storage allocation. You may choose to have a full mirror backup of the files, in which case each backed-up file or folder will consume 2x /project allocation (e.g. a 5GB file, mirrored, will consume 10GB of your /project allocation). You may also choose an incremental backup, in which case each backed-up file or folder will consume as much storage as necessary to store the incremental history (e.g. a 5GB file which is never changed will consume 5GB, while one which is entirely overwritten in between every weekly backup for a month will consume ~25GB)
* Files under /archive are backed up by PI request, similarly to /project. Please note that the 2/3 storage cost does not apply to mirror backups. A 2GB file backed up via mirroring on /archive will cost 2GB for the original, plus 3GB for the backup. A 2GB file backed up via incremental changes will cost the base 2GB plus the cost of storing the incremental history.

  See the BioHPC Cloud Storage Guide for more information.
  Email biohpc-help@utsouthwester.edu to request recovering files.
  
### How can I create a BioHPC account, and access all of the services?

Ensure with your department or center that you are eligible for membership with BioHPC. If you are not certain, please contact us. Once eligibility is confirmed, register for a BioHPC account  . Your account will not have full access to BioHPC services until you attend the mandatory new user training session held on the first Wednesday of each month from 10:30 AM - 12:00 PM on . The attendance list will be automatically taken once you attend the training session. Within two weeks, you will receive an e-mail notifying when your BioHPC account has been activated.
  
### Do I need to register for a training session before I attend?

No, you don't need to register separately for the training sessions.
  
### The system says my account has expired, what can I do?

This is because your password has expired. According to UTSW policy, you need to change your password annually. Click  to change your BioHPC password. 
  
### I suddenly cannot get access to BioHPC system, why is that?
  
In most case, it is because your password has expired. Please refer to the above question for solution. 
  
The situations you have may experience with an expired password are:

* **SSH:** Your account has expired; please contact your system administrator.
* **Lamella:** Access to your account on the server lamella.biohpc.swmed.edu has been denied.
* **FileZilla:** Failed to connect.
* **Network Drive:** Fail to connect.
* **Web Visualization GUI session:** Connection refused.
* **Thin Client:** Cannot login.
  
### How can I create a shared folder between two departments to share data?

Please provide us the information below: 

Which department will contribute the storage space required? We need assign a primary department to this folder.
How much storage space is needed? We need approval from the primary department chair to assign storage space.
Do you need a specific name for this folder? We will name it using the two PIs last names by default.
  
### My /project storage space is over quota, what can I do?
  
1) Decrease disk usage
You may want to move files to your /archive directory. Usage on /archive will be calculated only as 2/3 of the actual usage. The archive directory structure is laid out similarly to /project. The default quota is 5 TB per lab, but it can be increased.

2) Increase quota
Your PI can ask the department chair for approval to increase the lab quota on /project. We will increase the quota with the department chair's email approval.
  
### Submit jobs using SECONDARY GROUP for accounting purpose with multiple projects/groups.

By default when a user submits a job using sbatch, the system will account the CPU usages according to the user's primary group. In some situations, when a user has several secondary groups, and would like to run jobs and make the accounting of usage to the secondary group, the user can submit the job using the --gid=xxxx argument  (sbatch --gid=<the secondary group id> slurm_batch_script.sh) so that the usage can be accounted according to different collaborating groups/projects. 
