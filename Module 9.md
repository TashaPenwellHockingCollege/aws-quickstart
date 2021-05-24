# Section 1: AWS Well-Architected Framework

Cloud architects engage with decision makers to identify w/ business goals and capabilities that need improvement.
    * ensure alignment between tech deliverables of a solution and business goals
    * work w/ delivery teams that are implementing the solution to ensure tech features are appropriate
    
## AWS Well-Architected Framework
    * guide for designing infrstructures that are 
        1. secure
        2. high performing
        3. resilient
        4. efficient
    * Consistent approach to evaluating and implement cloud architecture
    * Way to provide best practices that are developed through lessons learned by reviewing customer architecture
    * organized into 5 pillars
        1. Operatonal Excellence
        2. Security
        3. Reliability
        4. Performance Efficiency
        5. Cost Optimization
     * each pillar include a set of design principles and best practices
     
     
 # Section 2:  Operational Excellent Pillar
      *FOCUS:  
          -run and monitor systems to deliver busienss value
          -continually improve supporting processes and procedures
          
      *KEY TOPICS
           -managing and automating changes
           -responding to events
           -defining standards to successfully manage daily operations
           
      *SIX DESIGN PRINCIPLES
            1.  Performa operations as code
            2.  Annotate documenttaion 
            3.  Make frequent, small, reversible changes
            4.  Refine operations procedures frequently
            5.  Anticipate failure
            6.  Learn from all operational events and failures
            
     ## Operational Excellence Questions
     PREPARE
          1.  How do you determien what your priorities are?
          2.  How do you design yoru workload so that you can understand its state
          3.  How do you reduce defects, ease remediation, and improve flow into production?
          4.  How do you mitigate deployment risk
          5.  How do you know that you are ready to support a workload
          
      OPERATE
          1.  How do you understand the health of a your workload?
          2.  How do you understand the health of your operations?
          3.  How do you manage workload and operations events?
          
      EVOLVE
          1.  How do you evolve operations?
          
  # Section 3:  Security Pillar
           * FOCUS
                 -Protect information systems and assets while delivering business value through risk assessments and mitigation strategies
           
           * KEY TOPICS
                  - identifying and managing who can do what (privilege management)
                  - establishing controls to detect security events
                  - protecting systems and services
                  - protecting confidentiality and integrity of data
          
          * SECURITY DESIGN PRINCIPLES
                  -implement a strong identify foundation (least privilege)
                  -enable traceability (integrate logs)
                  -apply security at all layers ("defense in depth" to all layers)
                        --i.e. edge networks, VPC, subnets, load balancer, every incstance, OS and application)
                  -automate security best practices (improve ability to securely scale more rapidly and cost effectively)
                  -protect data in transit and at rest (classify data into sensitivyt levels and use mechanisms like encryption, tokenization and access control where appropriate)
                  -keep people away from data (reduce risk of loss or modification of sensitive data due to human error.  create mechanisms and tools to reduce or eliminate need for direct access or manual processing of data)
                  -Prepare for security events (have an incident management process that aligns w/  organ requirements)
            * SECURITY QUESTIONS
               -IDENTITY AND ACCESS MANAGEMENT
                     1.  How do you manage credentials and authentiation?
                     2.  How do you control human access
                     3.  How do you control programmatic access?
               -DETECTIVE CONTROLS
                     1.  How do you detect and investigate security events?
                     2.  How do you defent agains emerging security threats?
               -INFRASTRUCTURE PROTECTION
                     1.  How do you protect your network?
                     2.  How do you protect your compute resources?
                -DATA PROTECTIONS
                     1.  How do you classify your data
                     2.  How do you protect your data at rest?
                     3.  How do you protect your data in transit?
                -INCIDENT RESPONSE
                     1.  How do you respond to an incident?
                     
# Section 4:  Reliability Pillar
         *FOCUS 
              -prevent and quickly recover from failures to meeting business and customer demand
         *KEY TOPICSS
               -Setting Up
               -Cross-project requirements
               -Recovery planning
               -Handling change
         *FIVE DESIGN PRINCIPLES
               1.  Test recovery procedures (test how systems fail and how recovery px)
               2.  Auto recover from failure (monitor systems for KPI and key system to trigger)
               3.  Scale horizontally to increase aggregate system avail (replace one large resource w/ multiple smaller resources to reduce impact of single point of failure)
               4.  Stop guessing capacity (monitor demand and essential usage)
               5.  Manage change in automation (use automation to make changes to infra)
         *RELIABILITY QUESTIONS
            -FOUNDATIONS
               1.  How do you manage service limits?
               2.  How do you manage your network topology?
            -CHANGE MANAGEMENT
               1.  How does your system adapt to changes in demand?
               2.  How do you monitor your resources?
               3.  How do you implement change?
            -FAILURE MANAGEMENT
               1.  How do you backup data?
               2.  How does your system w/stand component failure?
               3.  How do you test resilience?
               4.  How do you plan for disaster recovery?

# Section 5:  Performance Efficiency Pillar
            *FOCUS
               -use IT and computing resources efficiently to meet system requirements and mainting that efficiency as demand changes and technologies evolve
            
            *KEY TOPICS
               -Selecting the right resource types and sizes based on workload requirements
               -Monitoring performance
               -Making informed decision to maintain efficiency as business needs evolve
            *PERFORMANCE EFFICIENCY DESIGN PRINCIPLES
               1.  Democratize advanced technologies (consume tech as a service; not everyone has same skills in tech community - in the cloud, these technologies become services that teams can consume.  Consuming techn enables teams to focus on product development instead of resource provision and managment)
               2.  Go global in minutes (deploy system in mult Regions for lower latency and better costs)
               3.  Use serverless architectures (remove op burden of running/maintaing servers, lower transaction costs)
               4.  Experiment more often (perform comparitve testing w/ different instance types, storage, configurations)
               5.  Have mechanical sympathy (use tech approach that aligns best to what trying to achieve)
               
             *PERFORMANCE EFFICIENCY QUESTIONS
               -SELECTION
                  1.  How do you select the best performing architecture
                  2.  How do you select your compute solution?
                  3.  How do you select your storage solution?
                  4.  How do you select your database solution?
                  5.  How do you select your networking solution?
                -REVIEW
                  1.  How do you evolve your workload to take advantage of new releases?
                -MONITORING
                  1. How do you monitor yoru resources to ensure they are performing as expected?
                -TRADEOFFS
                  1.  How do you use tradoffs to improve performance
              
# Section 6:  Cost Optimization Pillar
         *FOCUS
            -run systems to deliver bus value at lowest price point
         *KEY TOPICS
            -understand/controlling when money is being spent
            -select most appropriate and right number of resource types
            -analyzing spending over time
            -scaling ot meet business needs without overspending
         
         *COST OPTIMIZATION DESIGN PRINCIPLES
            1.  Adopt a consumption model (pay only for computing resources you require)
            2.  Measure overall efficiency (measure business output of workload and costs of resources to get it)
            3.  Stop spending money on data center operations (AWS does heavy lifting w/ servers)
            4.  analyzing and attribute expenditure (identify sys usage and costs and attribute costs to workload owners)
            5.  use managed and application-level services to reduce cost of ownership (use manage and application level services to reduce costs of ownership)
            
         *COST OPTIMIZATION QUESTIONS
            -EXPENDITURE AWARENESS
               1.  How do you govern usage?
               2.  How do you monitor usage and costs?
               3.  How do you decommision resources?
               
             -COST EFFECTIVENSS RESOURCES
               1.  How do you evaluate cost when you select services?
               2.  How do you meet cost targets when you select resources type and size?
               3.  How do you use pricing models to reduce costs?
               4.  How do you plan for data transfer charges?
             
             -MATCHING SUPPLY AND DEMAND
               1.  How do you match supply of resources with demand?
               
             -OPTIMIZING OVER TIME
               1.  How do you evaluate new services?
               
# SECTION 7:  RELIABILITY & AVAILABILITY
              -"plan for failure"
              - need to think in statistical terms that "everything will fail"
              -need to build architectures to withstand failure
              -RELIABILITY: measure of system's ability ot provide functionality when desired bythe user
              -SYSTEM:  includes all system components HW, firmware, and SW
              -PROBABILITY:  that your entire system will function as intended for a specified period
              -MEAN TIME BETWEEN FAILURES (MTBF): statistical number; total time in service/number of failures 
                     i.e. Bring on an application Monday at Noon, application fails on Friday at noon and is not repaired until Monday at noon ==> Time to Failure (lenght of time app is availabile is 96 hours).  Time to repair is Friday - Monday = 72 hours
                     Failure repeats the next Friday and spend another 72 hours fixing it and the cycle continues to repeat cycle of failure-repair-restore every week
                     Can now calculate average of these numbers
                           >Mean time to failure is 96 hours
                           >Mean time to repair is 72 hours
                           ==>Mean time between failures is 168 hours or 1 week which is the sum of the mean time to failure and the mean time to repair
                     
              ## AVAILABILITY DEFINED AS
                  * Normal operation time / total time
                  * a percentage of uptime (i.e. 99.9%) over time (i.e. 1 year)
                  * Number of 9s
                  
              ## HIGH AVAILBILIGY
                    * System can withstand some measure of degradation while still remaining available
                    * Downtime is minimized
                    * Minimal human intervention is required
                    
               ## AVAILBILITY TIERS
                  * Availabilty requires will vary depends on type of application
                  *review tables of apps common at each avail tier
                  
                ## FACTORS THAT INFLUENCE AVAILABILITY
                  -FAULT TOLERANCE
                     --The built-in redundancy of an application's components and its ability to remain operational. 
                     --does not address SW failures
                  -SCALABILITY
                     --Ability of an application to accomodate increases in capacity needs without changing design
                     
                  -RECOVERABILITY
                     --Process, policies, and procedures that are related to restoring service after a catastrophic event
                  
                  
        
# SECTION 8:  AWS TRUSTED ADVISOR
      *AWS TRUSTED ADVISOR
         -Online tool that provides real-time guidance to help provision your resources following AWS best practices
         -can start using as soon as start implementing architecutres
         -don't need to have a fully build production-ready environment
         -Looks at your entire AWS environment and gives your real time recommendation in 5 categories
            1.  Cost optimization
                  -looks at resources usage and makes recommendation to help optimize costs (i.e. eliminate unused/idle resources)
            2.  Performance
                  -checking service limits, looking at provisioned throughput, and monitoring for overutilized instances
            3.  Security
                  -help improve ecurity by identifying gaps need to close and security features need to enable
            4.  Fault Tolerance
                  -help increase availability and redunandy in AWS application to take advantage of auto scaling, health checks, multi-AZ deployments and backup capabilities
            5.  Service Limits
                  -checks for service usage that is more than 80% of service limit; based on snapshot so numbers could differ; limit and usage data can take up to 24 hours to reflect any changes
                  
 
