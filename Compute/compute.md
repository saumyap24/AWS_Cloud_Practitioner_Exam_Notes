- [EC2 Overview](#ec2-overview)
- [VMs, Containers, Serverless](#vms-containers-serverless)
- [High Performance Computing (HPC)](#high-performance-computing)
- [Edge and Hybrid](#edge-and-hybrid)
    - [What is Edge Computing ?](#what-is-edge-computing)
- [Cost & Capacity Managemnet](#cost-and-capacity-managemnet)
---

## EC2 Overview
---
 - <i> allows to launch Virtual Machine </i>
 - when this virtual machine is launched it is called an <i>"instance"</i>

 - <b> What is Virtual Machine ?</b>
    - It is a emulation of a Physical computer using software
    - Server virtualisation allowd to "CREATE" , "COPY" , "RESIZE" or "MIGRATE" the server
    - Multiple VMs can run on same physical server so that costs could be shared between other customers
    - When we launch a Virtual Machine we call it "instance"
- EC2 is <i> highly configurable server </i> where we can choose AMI that affects options such as:
    - amount of CPUs
    - amount of RAM memory
    - Network Bandwidth
    - Operating System
    - attach multiple hard drives for storage eg. Elastic Block Store (EBS)
- EC2 is considered as the <i> backbone of AWS </i> because majority of AWS services are using EC2 as their underlying servers. eg. S3, RDS, DynamoDB,Lambdas
---
## VMs, Containers, Serverless
---

- <b> Virtual Machine </b>
    - <b> Amazon LightSail </b>
        - managed virtual server service
        - "friendly" version of Ec2 Virtual Machines
        - {when you want to launch a linux or windows server but don't have AWS knowledge eg. Launch a Wordpress}

- <b> Containers </b>
    - Virtualising a Opearating System (OS) to run multiple workloads on a single OS instance
    - Containers are generally used in <i> Microservices Architecture </i> (when the application is divided into smaller applications that talk to each other)

    - <b> Elastic Container Service (ECS) </b>
        -  <i> container orchestration service </i> that supports Docker containers
        - Launches a cluster of server on EC2 instances with Docker installed

    - <b> Elastic Container Registry (ECR) </b>     
        - <i> Repository for container images </i>
        - In order to launch a conatiners you need an image
        - An image just means a saved copy
        - A repository means a storage that has version control
    
    - <b> ECS Fargate </b>
        - <i> A serverless orchestration container service </i>
        - Same as ECS but <u> expects to pay-on-demand per running conatiner  </u>
        - With ECS have to keep a EC2 server running even if no containers are running 
        - AWS manages the underlying sever, so you don't have to scale or upgrade the EC2 server
    
    - <b> Elastic Kubernetes Service (EKS) </b>
        - <i> a fully managed Kubernetes service </i>
        - Kuberenetes (K8) is an open source orchestration software created by Google and is generaly the standard for managing microservices 
        - {when you need to run Kubernetes as a service}
    
- <b> Serverless </b>
    - <b> AWS Lambda </b>
        - <i> A serverless functions service </i>
        - <I> Can run Code </i> without provisioning or managing severs
        - Upload small pieces of Code, Choose much memory and how long function is allowed to run before timing out
        - Charged based on the runtime of the serverless function rounded to the nearest 100ms.
---
## High Performance Computing (HPC)
--- 

- <b> The Nitro System </b>
    - Combination of <i> dedicated hardware and lightweight hypervisor</i> enabling faster innovation and enhanced security. 
    - All new EC2 instance types use the Nitro System
        - Nitro Cards :-  Specialized cards for VPC, EBS and Instance Storage and Controller Card
        - Nitro Security Chips :- Integrated into motherboard. Protects hardware resources.
        - Nitro Hypervisor :- lighweight hypervisor Memory and CPU allocation Bare Metal-like performance.

- <b> Bare Metal Instance </b>
    - You can launch EC2 instances without hypervisor so that workloads run directly on the hardware for max performance and control.
    - <b> M5 and R5 </b> EC2 instances <u> run are bare metal </u>
    - <b> Bottlerocket </b>
        - A Linux based open source built for running containers on VM or Bare metal hosts 
    - <b> What is High Performance Computing (HPC)? </b>
        - A cluster of hundreds of thousands of servers with fast connections between each of them with the purpose of boosting computing capacity.
        - When you need a SuperComputer to perform computational problems too large to run on a standard computers or would take long
            - <b> AWS ParallelCluster </b> - <i>AWS-supported open source cluster management tool </i> that makes it easy to deploy and manage High Performance Computing (HPC) clusters on AWS.
---
## Edge and Hybrid 
---

 - ### <b> What is Edge Computing ? </b>
    - Pushing comuting workloads outside of your networks run close to destination locations
    - eg. Pushing computing to run on Phones, IOT devices or external servers not within your cloud network.

- <b> What is Hybrid Computing? </b>
    - Able to run workloads on both on-premise datacenter and AWS VPC (virtual private cloud)
        - <b> AWS OutPosts </b> 
            - Physical rack of servers 
            - Allows to use AWS API and services such as EC2 right in your datacenter
        - <b> AWS Wavelength </b>
            - Allows <i> to build and launch your application in a telecomm datacenter </i> 
            - By doing this applications have ultra-low latency since they will be pushed over a 5G Network and be closest as possible to end user 
            - eg. Verizon, Vodafone
        - <b> VMWare Cloud on AWS </b>
            - Allows to <i> manage on-premise virtual machines using VMWare </i> as EC2 instances.
            - The datacenter must be using VMWare for Virtualization 
            - eg. VMWare Sphere
        - <b> AWS Local Zones </b>
            - <i> Edge datacenter located outside of AWS region </i> so you can use AWS closer to end destinations
            - When you need faster computing, storage and databases in populated areas that are outside of an AWS region
---
## Cost and Capacity Management
---

- <b> EC2 Spot Instances, Reserved Instanced and Savings Plan </b>
    - Ways to save on computing
        - by paying full or partially , 
        - (or) by commiting to a yearly contracts 
        - (or) by being flexible about availability and interrruption of computing service
- <b> AWS Batch </b>
    - Plans , Schedules, and <u> executes batch computing workloads </u> accross the full range of AWS compute services, can utilize Spot Instance to save money

- <b> AWS Compute Optimizer </b>
    - suggests how to <i><u> reduce costs and improve performance </U></i> by using machine learning to analyze you previous usage history

- <b> EC2 Autoscaling Groups (ASGs) </b>
    - <u> Automatically adds or remove EC2 servers </u> to meet the current demand of traffic.
    - Will save money and meet capacity since you only run the amount of servers you need

- <b> Elastic Load Balancer (ELB) </b>
    - Distributes traffic to multiple instance, can re-route traffic from <u> unhealthy instance to healthy instances</u>.
    - Can route traffic to EC2 instances running in different Availability Zones

- <b> AWS Elastic Beanstalk (ELB) </b>
    - <u> Easily deploys web applications</u> without developers worrying about setting up and understanding the underlying AWS Services
    - eg. Heroku





