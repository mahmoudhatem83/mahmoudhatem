STC ACS
--------

Operations will be distributred into 2

- admin tasks 
- secuirty policy and tuning 


-----

Communication matrix to be added to the design document 

what we need to do to allow a full subnet 

Updating Implementation plan to match what was shared by Ammar


Integration with SIEM Solutions 
Integration with Pipeline ?
Touchpoints between ACS and Pipeline
Integration with  image stack, Nexus, image registry 


Sherif points :
- phsyical design
- logical design
- availability 
- managment plan 
- how it will be managged 
- ips and console and so 
- flow from adminsitartor to end user 
- traffic flow from ACS to SIEM solution 
- accounts for managing ACS - do we need to integrate with Active directory 
- integrating with SNMP ?
- email alarms 
- intergation with performance tools
- as ACS is on openshift to mention openshift architicture (OCP on vmware and IPs ...)
- product lifecycle
- capacity and performance , scale and managment ratio between pods and clusters and so 
- integration with devops stack CICD 
- mention different policeis and the types of it , and which is doing what 




Devops team to manage the platform
secuirty policies to be managed by security 








number of vcore per host and the VM not to exceed the number of vcore 
2 numa 
disk requirmnets to be not less than 3000 IOPS 
affinity roles for master nodes
each master with a separate datastore 
OCS in different failure domain and separtae datastore 

hardware version to be 15 +
vcenetr 6.5 or even 7 

disk.uuid to be enabled 

senetive high in case not overcommit environment 
en case relaxed then sensitive high 


fio script 
offical script 











who will handle 
Creation of Policies and Network polices
Actions based on violation events 


configuring egress IP for ACS 










----------







Vulnerability managment sceanrios

- check the top risk images
- check the images that has CVE with high rate >7 
- some of them is fixable 
- Play around with docker layers
- check the image versions and date 
- play around with defer and false positive
- check the approval section 
- the critical CVE is the one that is involved with deployment 
- you need to look at the one with high risk factor


Go to Risk 
- in Risk priorities are the key
- click on any of the risks and see the detail at the side
- example of risks are
    - CVEs
    - Network ports
    - Service exposure 
    - privilage container which means successful attacker will have access to underlying host network and filesystem and other containers running on the same host 
- check the RBAC section 
- check if any risk like service account with admin privilage or so 

- go to process Discovery
  - check the running process and if showing something out of the baseline you can choose to add it
  - if there is a policy violation you can click on the header to show the time stamp for the violation 

filters are very useful 
filter with process name and CVE number and then you can create policy if you want 



Go to Network Graph 
- filter the cluster and the namespace 
- click on the namesapce to see the involved deployments
- navigate to deployment to check the deference between baseline and the additional
- you can add them to baseline
- click on the Flow - Allowed - Active and All
- explain the legend 
- click on network simulator 
- generate a network policy and check if you can apply it 



Go to Violation 
we don't want to make operations team deal with violation as a to-do task list 
the violation are per deployment and not per pod 

Go to compliance 
- check different benchmarks 
- for example check the NIST 800-1900 and click on image vulnerabilty
  if we have configured a policy against vulneable images >7 then you can find this benchmark as 100%

play around by changing a policy to be compliant with one of the benchmarks and then apply it and see the change in the benchmark 

Integrating the OpenShift Compliance Operator with ACS



Configuration Management
It brings together information about all your 
- clusters
- namespaces
- nodes
- deployments
- images
- secrets
- users
- groups
- service accounts
- roles 

Show RBAC, users and groups


Policy 
Policy cover Build , deploy and runtime
Click on the Red Hat Package Manager in Image Policy to view policy details. (use the filter)

Test image policy?
test secret delete ?
test project ID ?





New features
- scan images before pushing to registry
- Identify inactive software components



roxctl is the command line to manage ACS
for the evaluation of images and resources against policy definitions held on the RHACS



do we have a restriction of having the data for a year 
getting block downlaod a file and execute a command based on this downloaded file









