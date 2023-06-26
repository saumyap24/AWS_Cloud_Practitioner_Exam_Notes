- [EC2 Overview](#ec2-overview)
- [VMs, Containers, Serverless](#vms-containers-serverless)
- [High Performance Computing (HPC)](#high-performance-computing)

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

## High Performance Computing (HPC)
--- 

- <b> The Nitro System </b>
    - Combination of <i> dedicated hardware and lightweight hypervisors</i> enabling faster innovation and enhanced security. 
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
        - When you need a SuperComputer 




