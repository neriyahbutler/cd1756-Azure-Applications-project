Since we're deploying in the lower environment and the solution isn't going out to any stakeholders, the compute doesn't need to be something dedicated for production. We don't have a need to configure our own infrastructure, especially since the language we're using is one of the multiple supported languages. Additionally, we do not have a need to install software onto a server. In order for VMs to be a viable option, we'd need to have some sort of functionality developed in an unsupported language, or a need to install software.
 
For the sake of this portion of the project, let's compare the best suited VM and App Service plan based on the details shared earlier. Considering the following details mentioned earlier:
 - Solution won't be deployed to stakeholders, I'm the only consumer
 - We will not be deploying the solution in a production environment
 
As a result, we can look at the Basic B2 App Service Plan and B2 V2 VMs, as both align with the details mentioned.
 

Plans
1 - B2 App Service (Basic, B1)
2 - B2 V2 VM (B2pts v2)

Cost
1 - $54.75/monthly
2 - $14.31 /monthly

Scale
1 - Built-In (Auto scale), Load balancer (Integrated)
2 - VM Scale Sets, AZ Load Balancer

Availability
1 - Azure Traffic Manager, AZ Front Door, Cross-region Load Balancer
2 - Traffic Manager, Azure Front Door


One thing offered by the VM plan is its ability to burst to significantly higher CPU utilization, which isn't necessary for our solution. In the scenario where our solution IS in need of a scaling up, the burst may provide some temporary aid but we'd ultimately need to setup a VM scale set in order to "properly" scale.
 
Alternatively, App Services already provide this support as they auto scale. By utilizing App Services I only need to worry about deploying the app service without dedicating any time on setting up/maintaining the infrastructure. While app services do have a ceiling on how much they can scale vertically (which may be an indication of when it is necessary to switch to VMs), this is not a concern for this solution.
 
 The same can be said for the availability of the App Service regarding convenience. Unlike VMs, they are automatically built-in and don't require any knowledge on how to set them up which makes development easier for us. For example, the creation of a load balancer for VMs would need to be done manually on top of already creating several VMs. App Services already have this functionality implemented.
 
The only downside between the two choices is the cost. The VM cost is significantly cheaper than the App Service alternative. In my opinion, I feel that the tradeoff between the price difference is worth it. The approximate forty dollar difference cuts out the need to do any work related to maintaining the infrastructure. This ranges from keeping the OS up to date, handling the installation of software along with some network controls (more than what we'd have to manage with the PaaS approach).
 
As a result, I am going to go with the App Service/B2 App Service option.
