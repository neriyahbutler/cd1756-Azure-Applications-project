For the purpose of this project, we do not need a powerful compute in order to host the web app, especially since this solution won't be deployed to stakeholders. Due to this, I will be using the lowest pricing tier.

For the purpose of this exercise, we'll be looking at the Basic Service Plan "B2" for App Services and "B2 V2" for VMs.

B2 - $25.53 monthly (App)
B2Is V2 - $30.3680 monthly (VMs)

One thing offered by the VM plan is that it is able to "burst" to significantly higher CPU utilization, which isn't necessary for this particular scenario. While this VM plan is able to do "bursts" and VM scale sets are able to support "proper" scaling, App Services are capable of the same thing with less setup and work. By utilizing app services, I would only need to worry about deploying the app service without dedicating any time on setting up/maintaining the infrastructure. I would not need to worry about setting up high availability, as it is automatically implemented. On top of the lower amount of responsibilities, the cost of utilizing the "B2" App Service plan would lessen the amount of money I'd have to pay for my Azure account.

However in the scenario where we must move up from App Services due to increased demand, we can use a "Dads v7-series" VM. From the documentation I referenced earlier, it has temporary storage capabilities which may come in handy with our caching. I personally believe this would be of more benefit compared to "B2Is V2" (aside from the fact that it is dedicated for lower environments) as we'd be able to get more value consistently from the temporary storage capabilities (at least I would think so). In addition to this, the plan I mentioned provides the best specs at the best price compared to the other plans that offer temporary storage with savings applied to the costs.
