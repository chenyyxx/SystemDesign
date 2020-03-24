# My system Design Note

## Cracking System Design Interview: Approach

    1. Requirements Clarifications
        - user need
    2. Back-of-the-envelope estimation
        - Estimate the scale based on the Step1
    3. System Interface Definition
    4. Defining Data Model
    5. High-Level Design
    6. Detailed Design
    7. Identifying and Resolving Bottlenecks 

## Distributed System
    1. Scalability
        - Reasons to scale: increased data volume/ increased amount of work
        - Need to minimize performance loss due to scaling
        - Performance loss? Atomic nature of the task / flaw in system design
        - Horizontal vs. Vertical Scaling
            - Horizontal: adding more servers into pool of resources
                - Easier to scale dynamically
                EG: Cassandra and MongoDB => easy add servers
            - Vertical: adding more power (CPU, RAM, Storage, etc.) to existing server
                - Limited to capacity in a single server
                - involves downtime, with upper limit
                EG: MySQL => easy switch from smaller to bigger machine
    
    2. Reliability
        - A distributed system is considered reliable if it keeps delivering its services when one or several of its software or hardware components fail.
            - Key of distributed system: one machine fail, replace with other healthy one
        - Approach: achieve through storing redundant counterpart (replication) of both the software components and data in different machines
            - has a cost => pay to achieve such resilience to avoid failures
    
    3. Availability
        - The time a system remains operational to perform its required function in a specific period
            - percentage of time a system/ service/ machine remains operational under normal conditions.
            - Takes into account maintainability/ repair time, spares availability and other logistics considerations (downtime) 
            - A system is reliable => it is available, but if it is available, it is not necessarily reliable
    4. Efficiency
        - Standard Measurements
            a. Reponse Time (Latency): the delay to obtain the first item
            b. Throughput (or bandwidth): the number of items delviered in a given time unit (e.g., a second).
        - Unit Cost:
            a. Number of messages globally sent by the nodes of the system regardless of the message size.
            b. Size of messages representing the volumn of data exchanges.
    5. Serviceability or Manageability
        - How easy it is to operate and maintain: simplicity and speed with whic ha system can be repared or maintained.
            - ease of diagnosing/ understanding problems
            - ease of making updates or modifications
            - how simple the system is to operate
        - Early detection of faults can decrease or avoid system downtime.


## Load Balancing
