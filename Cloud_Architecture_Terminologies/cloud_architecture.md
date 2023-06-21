- [Cloud Architecture Terminologies](#cloud-architecture-terminologies)
    - [High Availability](#high-availability)
    - [High Scalability](#high-scalability)
    - [High Elasticity](#high-elasticity) 
    - [Fault Tolerance](#fault-tolerance)


## Cloud Architecture Terminologies
---
- <b> What is Solutions Architect? </b>
    - A role in technical organisation that architects a technical solution using multiple systems via researching, documentation and experimenting.
    - Business Factors:
        - <u>(Security)</u> How secure is this solution?
        - <u>(Cost)</u> How much is this getting to cost?
- <b> What is Cloud Architect?</b>
    - A solutions architect that is solely focused on getting technical solutions using cloud services.
    - Business Requirements in designing the architecture:
        - <b> High Availability </b>
        - <b> Scalability </b> 
        - <b> Elasticity </b> - to grow or shrink to meet demand
        - <b> Fault Tolerance </b> - to prevent failure
        - <b> Disaster Recovery </b>

## High Availability
---

- <i><u> no single point of failure</u></i>
- running workload across multiple AZs such that they are always available when any one of them fails --- Applications remains always available

 <img src="../images/cloud_architecture/availibilit_zone(1).png" width="50%"/>

    - It is achieved by <b>Elastic Load Balancer</b>
        - Distributes <i>evenly </i> traffic accross multiple serveers in one or more data center
        - if data center is not available it will route the traffic to available data center
        - atleast two load balancers up and running
        - maintaining the thresholds of the load balancer
        
       
## High Scalability
---

- <i>Increase capacity </i> based on increasing demand or traffic memory and computing power
<img src="../images/cloud_architecture/high_scalability.png" width="50%"/>

## High ELasticity
---
- <i> automatically </i> increase or decrease capacity based on current demand of traffic, memory and computing power
    - <b> Horizontal Scaling</b>
        - Scaling <i> Out </i> - add more servers of same size
        - Scaling <i> In </i> - Remove underutilized servers of the same size
        
        <img src="../images/cloud_architecture/high_elasticity.png" width="50%"/>

    - <b> Vertical Scaling</b>
        - generally hard with traditional architecture so only horizontal scaling is supported for Elasticity
- To accomplish highly elastic groups is achieved with 
    - <b> Auto Scaling Group (ASG) </b>
        - automatically add ro remove servers based on scaling rules you define based on metrics

## Fault Tolerance
---
