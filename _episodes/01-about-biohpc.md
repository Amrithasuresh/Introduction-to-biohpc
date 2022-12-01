---
title: "About BioHPC @ UT Southwestern"
teaching: 20
exercises: 0
questions:
objectives:
- "BioHPC membership"
- "Our services"
- "BioHPC Business Model"
keypoints:
- "When you initialize a Git repository in a directory, Git starts tracking the changes you make inside that directory."
- "This tracking creates a history of the way the files have changed over time."
- "Git uses a two-step process to record changes to your files. Changes to files must first be added to the staging area, then committed to the Git repository."
---

### Overview

The UT Southwestern BioHPC team provides and maintains high-performance computing, storage and client systems for the UTSW research community. BioHPC offers hardware for cluster computing, large data storage, file sharing inside and outside the campus, and a portal to integrated desktop and thin-client computing in individual labs. These offerings are now made available to users across campus, both in the basic sciences and the clinical arenas.

The BioHPC Business Plan summarizes how academic and clinical teams may interact with this infrastructure, including details about the process of gaining membership to the BioHPC.

#### BioHPC membership

* **Advanced Imaging Research Center (AIRC)**
* **Bioinformatics Core Facility (BICF)**
* **Department of Biochemistry**
* **Department of Bioinformatics**
* **Department of Biophysics**
* **Department of Cell Biology**
* **Children's Medical Center Research Institute (CRI)**
* **Cryo-Electron Microscopy Facility (CryoEM)**
* **Department of Anesthesiology and Pain Management (DAPM)**
* **Department of Population and Data Sciences (DPDS)**
* **Cecil H. and Ida Green Center for Reproductive Biology Sciences (GCRB)**
* **Green Center for Systems Biology**
* **Hamon Center for Therapeutic Oncology Research (HCTOR)**
* **Department of Immunology**
* **Department of Internal Medicine**
* **Eugene McDermott Center for Human Growth and Development (MCHGD)**
* **Department of Microbiology**
* **Microbiome Research Laboratory (MRL)**
* **Peter O'Donnell Jr. Brain Institute (OBI)**
    * **Center for Alzheimer's and Neurodegenerative Disease (CAND)**
    * **Neuroinformatics Core**
    * **Department of Neurological Surgery**
    * **Department of Neurology**
    * **Department of Neuroscience**
    * **Department of Physical Medicine and Rehabilitation (PMR)**
    * **Department of Psychiatry**
* **Department of Pathology**
* **Pediatric Cancer Data Core (PCDC)**
* **Department of Radiology**
* **Department of Radiation Oncology (RADONC)**
* **Structural Biology Laboratory (SBL)**
* **Harold C. Simmons Comprehensive Cancer Center (SCCC)**
* **Department of Surgery**
* **Touchstone Diabetes Center (TDC)**
* **Texas Institute for Brain Injury and Repair (TIBIR)**
* **Department of Urology**


### Our Services  

* **Current BioHPC services include**
* **Enables you to contribute to, collaborate on, and support digital research projects**
* **A 28,000 CPU Cores HPC cluster, Nucleus, coupled to very fast storage systems**
* **60 large-memory GPU equipped nodes for massively parallel programs using the NVIDIA CUDA toolkit**
* **5,400TB high-end (30-40 GB/s) Lustre filesystem (/project), and 5,530TB (5.4PB) high-end GPFS parallel filesystem (/work and /archive)**
* **A wide range of installed software including compilers, MPI libraries, Matlab, R, Python, common bioinformatics software and the SBGrid distribution**
* **Provision of Linux workstations and thin-clients connected to BioHPC systems**
* **Virtual machine images for access to other operating systems**
* **Cloud-based file storage, including an external file transfer system**
* **Git repository hosting using GitLab for software version control**
* **A comprehensive, web-based user portal for access to news, status, training, and other resources**
* **NGS Pipeline - a customized web-based pipeline for performing common NGS workflows using the BioHPC cluster**
* **Galaxy - an installation of the Galaxy platform configured to use BioHPC systems**


### BioHPC Cloud
 
Compared to traditional HPC facilities, BioHPC aims to be easy-to-use for all of our users regardless of computing experience. Though the heart of our systems is a high-performance compute cluster with fast storage, we offer a wide range of services. The BioHPC Cloud encompases all of our systems and services, with access to:

* **Simple web-based tools via the BioHPC Portal**
* **Specialized, research-focused web applications, e.g. Astrocyte**
* **Thin-client and workstation computers that are directly connected to the Nucleus compute cluster**
* **Virtualized servers providing access to a multitude of research software**
* **Traditional remote access using a command-line terminal and file transfer clients**



### Nucleus Compute Cluster

Our main compute facility is nucleus, a 800 node heterogenous compute cluster, consisting of:

### Lysosome Storage System

**Lysosome** is our primary high-performance bulk storage consisting of 5.4 PB raw storage provided by a Data Direct Networks SFA12X system, and an additional 960TB of raw storage provisioned with Dell PowerVault RAID hardware. 

Our Data Direct Networks SFA12K system uses dual active-active storage controllers, connected to multiple storage enclosures. Providing raw speeds of 80-90GB/s the storage is configured to host a Lustre parallel filesystem and is connected to the nucleus cluster with multiple inifiniband and 10Gb ethernet links. 82 Object Storage Targets (backed by the DDN storage) are aggregated into a single high performance filesystem, with operations directed by a Meta Data Target (MDT). The architecture is well suited to typical workloads in BioHPC, which operate on large image and sequence datasets.

### Endosome Storage System

**Endosome** is our off-site high-performance bulk storage consisting of 14 PB raw storage provided by IBM Elastic Storage Solution. Endosome uses IBM GPFS file system and locates at the QTS site at Irving, TX. This storage system is connected to our Nucleus cluster and Lysosome storage using high speed fibres across. Currently, it provides the /work and /archive file spaces for users and off-site backups of /home2 mirrors, /project incrementals and other web services for DR. This storage system has >1000 14 TB hard drives in 12 enclosures providing ~10 PB usable space. The actual aggregated IO throughput is ~60 GB/s.

### Lamella Cloud Storage Gateway

**Lamella** is our cloud storage gateway, providing easy access to files stored on BioHPC from Windows, Mac or Linux clients, over the web or on a smartphone. The Lamella web interface lamella.biohpc.swmed.edu at provides an easy-to-use site, similar to dropbox, to upload, download, manage and share files. Each user has an allocation of cloud storage and can also directly access their home, project, and work allocations. This service also supports file synchronization between computers using the OwnCloud client.

Direct access to files in home, project, and work locations is possible by mounting shared drives under Windows, Mac OS X, or Linux. Lamella shares these directories using SMB, with transfer rates up to 100MB/s for users on the campus 1 Gbps network and higher speeds available via the campus 10 Gbps network. FTP access to storage is also available via the Lamella gateway.

### BioHPC Cloud Clients

**BioHPC Cloud Clients** are computers running Linux, integrated into the BioHPC cloud. These systems provide a graphical Linux desktop and have direct access to BioHPC storage over the campus 10 Gbps network. All software available on the BioHPC cluster can be used on the cloud clients, which are ideal for developing and testing code and analysis workflows. Scripts and programs can be run locally on the client or directly submitted to the nucleus cluster using the command. Access to Windows applications is possible with virtualization.

Two models of cloud client are available. The thin-client is a small desktop device, while the workstation is a larger tower PC. Currently, we have >70 BioHPC Cloud Clients campuswide. The workstation has a more powerful CPU than the thin-client and has an internal GPU card. The workstation is recommended for users running local analyses regularly or developing GPU code.

### IB Network

BioHPC Compute Nodes are interconnected via an Infiniband network in a fat-tree topology. The 10 HDR central swithes provide up to 80 Tbps total bandwidth. We are using HDR, EDR, FDR cables between 25 Mellanox switches and nodes and fiber cables between switches. The supporting port speeds can reach 56 Gbps and 100 Gbps respectively.

### BioHPC Business Model

* The UT Southwestern BioHPC team provides and maintains high-performance comuting, storage, and client systems for the UTSW research
community

* The business model can be summarized as "By the users - For the users"
   * BioHPC team works directly with Department chair or administrator on resource requirements
   * Department chair or administrator internally coordinates with PIs on the total expected amount of compute resources and storage

* Questions? Please reach out to us: biohpc-help@utsouthwestern.edu

