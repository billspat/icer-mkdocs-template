# HPC Glossary

**Program** – code stored on a computer intended to fulfill a certain
task

-   There are many types of programs:
    -   Part of the operating system and help computer function
    -   Fulfill a particular job are called **applications**
-   Typically stored on disk (*g.*, hard drive)
-   A program needs memory and various **operating system** resources
    (*g.,* peripheral interfaces) to run

**Operating System** – manages all resources needed for a program
(*e.g.*, macOS)

**Process** – program with all necessary resources loaded into memory

-   When a program is run, it is loaded into memory which makes it
    accessible for processing by the computer’s central processing unit
    (CPU)
-   There can be multiple instances of a single program, and each
    instance of that running program is a **process**
-   Each process has a separate memory address space, which means that a
    process runs independently and is isolated from other processes
-   This independence of processes is valuable so that a problem with
    one process cannot cause havoc with another process

**Central processing unit (CPU)** - logical hardware unit capable of
executing a single process (*i.e.*, gets instructions then performs
calculations)

-   Made up of:
    -   **Processor** is a device that processes program instructions to
        manipulate data
    -   **Socket** is an array of pins that connect processor to
        motherboard
-   Individual CPU processors now contain multiple **cores** for more
    efficient multi-tasking and parallel computing
    -   **Core** is the smallest hardware unit capable of performing a
        processing task
    -   Ex: dual-core processor has two cores

![A photograph of a CPU chip with the processor, socket and core highlighted.](attachments/22708580/67502089.png)

![A diagram showing the progression from silicon wafer, to uncut processor, to a full processor unit.](attachments/22708580/67502088.png)

**Thread** (of execution) is the smallest set of programmed instructions
that can be managed independently by an operation system. In general,
one thread is handled by one core.

As video gaming popularity increased, so did the need for more computing
power. To accomplish this a CPU can work with a **graphics processing
unit (GPU)**, usually found on a graphics card docked into the
motherboard, to quickly render high-resolution images and video
concurrently. A GPU gets its intense computing power from hundreds of
smaller cores capable of crunch application data in parallel. Multiple
GPUs can be installed on one graphics card or multiple graphics card can
be installed in one node to further improve computation power through
parallelism. After GPUs became popular for gaming, they were made fully
programmable to be useful in processing big science data. The resulting
**general-purpose graphics processing unit (GPGPU)** is used extensively
in supercomputing to increase speed and improve analysis of scientific
data.

  

**Node** is a single computer comprised of 1+ CPUs, memory, network
interfaces, etc.

**Cluster** is a group of nodes networked together so that a program can
run on them in parallel

**Parallel computing** is an umbrella term describing the use of
multiple computers or computers made up of multiple processors in
combination to solve a single problem

  

Within HPCC there are different types of nodes:

-   **Gateway nodes** are nodes used to enter the computer system:
    -   **Login -** login and non-intensive compute tasks (*e.*, moving
        files)
    -   **rsync -** data transfer to/from HPCC
-   **Development (dev) nodes** are nodes used to navigate file systems
    and compile, test, and schedule heavy computational tasks (*e.*,
    jobs)
-   **Compute nodes** are <u>clusters</u> that perform scheduled jobs
-   **Accelerator nodes** are nodes equipped with accelerated cards
    (*g.*, GPU or phi nodes)

  

**Secure Shell (SSH)** - network protocols and implementing suite of
utilities that provide a secure way to access and execute commands on a
remote computer over an unsecured network

**Remote synchronization (rsync)** - software utility for Linux systems
that efficiently sync files and directories between two hosts or
machines making ideal for transferring large files

**File system** – tree-like directory organization for storing many
files

  

#### For more information on these terms, check out the following videos: 

[What is ICER’s HPCC](https://mediaspace.msu.edu/media/What%20is%20ICER's%20HPCC/1_4imyb64w) (11min)

[HPCC System Layout](https://mediaspace.msu.edu/media/HPCC%20System%20Layout%20Overview/1_eh4u3h1n) (7min)

<!--
<div class="pageSectionHeader">

## Attachments:

</div>

<div class="greybox" align="left">

<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image2021-9-8_7-44-29.png](attachments/22708580/67502088.png)
(image/png)  
<img src="images/icons/bullet_blue.gif" width="8" height="8" />
[image2021-9-8_7-44-39.png](attachments/22708580/67502089.png)
(image/png)  

</div>
 -->
