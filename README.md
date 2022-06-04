<p align="center">
  <img src="banner.png">
</p>

## The Challenge
1. Read about the challenge and register at [#100DaysOfCloud.com](https://100DaysOfCloud.com)
2. Join the [Discord Channel](https://discord.gg/c6Db8nY)
3. Copy the [100DaysOfCloud/100DaysOfCloud Journey Template](https://github.com/100DaysOfCloud/100DaysOfCloud/generate)
4. Use the [Micro](Templates/000-DAY-ARTICLE-MICRO-TEMPLATE.md), [Short](Templates/001-DAY-ARTICLE-SHORT-TEMPLATE.md) or [Long](Templates/002-DAY-ARTICLE-LONG-TEMPLATE.md) Day Journey Template and document your day-to-day progress.
5. Update your main README to link back to your Day Journey article
4. If you need ideas go to [#100DaysOfCloudIdeas](https://github.com/100DaysOfCloud/100DaysOfCloudIdeas)

## How to use this template:
Fill in your details where you see this icon ✍️
We have provided a sample Day Journey entry staring at 0. You can delete this example.

## [✍️ Prasant Chettri] Journey

[✍️ Introduce yourself]
Prasant Chettri - Azure Cloud Solution Eng
[✍️ Tell us why you started this challenge]
Too find a way to share, learn and document all the learning I do for the certicifation. Lot of the tooling and resources does not get implemeted to production deployment, therefore, it is easy for forget them over the time. Joining this community, hopefully, help me from not forgetting my learning as I document them and also learn how the other cohorts in this community structuring their learniing that I could adopt to be more productive.
[✍️ Tell us where you want to be at the end of the challenge]
To me able figure out the way to implement most of the learning on lab and find some open community project to implement most of them outside teh work.

- [✍️ Link to your Twitter](https://twitter.com/charlaton2007)
- [✍️ Link to your LinkedIn](https://www.linkedin.com/in/prasant-chettri-865b5436)

## Stepping out the door

- [ ] ☁️ 1 > [My First Day](Journey/001/Readme.md)
- [ ] ☁️ 2 > [leaned AZ-700 Here is the summary as of April 13,22
Facts
VPN gateway requires 

VPN gateway (It creates a Linux appliance in Azure)
Local gateway connection 
GatewaySubnet /27 minimum one gets  assigned to appliance it could be two if failover connection with two appliance on prem and clouds are setup


Express route -
L3 connectivity with on prem and MS cloud through PE
IPVPN network, p-to P ethernet connection or through virtual cross-connection via an Ethernet Exchange
Connectivity to MS cloud services in all regions of geopol region
Premium addon - Global connectivity to MS services across all regions
Built-in redundancy by peering

Cloud exchange co-location - eg if Iron mountain could be co-location facility for MS cloud virtual cross-connection and it could offer layer 2 or 3 orss-connect

Point-to-point ethernet connections - connection between your site and MS

Any-to-any VPN 
Integrate WAN with IPVPN (MPLS VPN) 

Direct from ER - Through nearest MS global network peering location 




Route advertisement
When Microsoft peering gets configured on your ExpressRoute circuit, the Microsoft Edge routers establish a pair of Border Gateway Protocol (BGP) sessions with your edge routers through your connectivity provider. No routes are advertised to your network. To enable route advertisements to your network, you must associate a route filter.

In order to associate a route filter:

You must have an active ExpressRoute circuit that has Microsoft peering provisioned.
Create an ExpressRoute circuit and have the circuit enabled by your connectivity provider before you continue. The ExpressRoute circuit must be in a provisioned and enabled state.
Create Microsoft peering if you manage the BGP session directly. Or, have your connectivity provider provision Microsoft peering for your circuit.

P addresses used for Azure private peering
You can use either private IP addresses or public IP addresses to configure the peerings. The address range used for configuring routes must not overlap with address ranges used to create virtual networks in Azure.

IPv4:
You must reserve a /29 subnet or two /30 subnets for routing interfaces.
The subnets used for routing can be either private IP addresses or public IP addresses.
The subnets must not conflict with the range reserved by the customer for use in the Microsoft cloud.
If a /29 subnet is used, it is split into two /30 subnets.
The first /30 subnet is used for the primary link and the second /30 subnet is used for the secondary link.
For each of the /30 subnets, you must use the first IP address of the /30 subnet on your router. Microsoft uses the second IP address of the /30 subnet to set up a BGP session.
You must set up both BGP sessions for our availability SLA to be valid.



IP addresses used for Microsoft peering
You must use public IP addresses that you own for setting up the BGP sessions. Microsoft must be able to verify the ownership of the IP addresses through Routing Internet Registries and Internet Routing Registries.

Public peering (deprecated - not available for new circuits)

Dynamic route exchange
Routing exchange will be over eBGP protocol. EBGP sessions are established between the MSEEs and your routers.

Autonomous System numbers (ASN)
Microsoft uses AS 12076 for Azure public, Azure private and Microsoft peering. We have reserved ASNs from 65515 to 65520 for internal use. Both 16 and 32 bit AS numbers are supported.


Bidirectional Forwarding Detection
ExpressRoute supports Bidirectional Forwarding Detection (BFD) both over private and Microsoft peering. When you enable BFD over ExpressRoute, you can speed up the link failure detection between Microsoft Enterprise edge (MSEE) devices and the routers that your ExpressRoute circuit gets configured (CE/PE)

BFD is configured by default under all the newly created ExpressRoute private peering interfaces on the MSEEs. As such, to enable BFD, you only need to configure BFD on both your primary and secondary devices. Configuring BFD is two-step process. You configure the BF
Resetting your ExpressRoute Peerings might be helpful in the following scenarios:

You are testing your disaster recovery design and implementation. For example, assume that you have two ExpressRoute circuits. You can disable the Peerings of one circuit and force your network traffic to use the other circuit.
D on the interface and then link it to the BGP session.

Configure encryption over ExpressRoute

how to use Azure Virtual WAN to establish an IPsec/IKE VPN connection from your on-premises network to Azure over the private peering of an Azure ExpressRoute circuit. 

Traffic from on-premises networks to Azure

For traffic from on-premises networks to Azure, the Azure prefixes (including the virtual hub and all the spoke virtual networks connected to the hub) are advertised via both the ExpressRoute private peering BGP and the VPN BGP. This results in two network routes (paths) toward Azure from the on-premises networks:

One over the IPsec-protected path
One directly over ExpressRoute without IPsec protection
To apply encryption to the communication, you must make sure that for the VPN-connected network in the diagram, the Azure routes via on-premises VPN gateway are preferred over the direct ExpressRoute path.

The same requirement applies to the traffic from Azure to on-premises networks


Configure ExpressRoute and site to site coexisting connections
You can configure a Site-to-Site VPN as a secure failover path for ExpressRoute.
Alternatively, you can use Site-to-Site VPNs to connect to sites that are not connected through ExpressRoute.


Create a zone redundant VNet gateway in Azure availability zones


Gateway SKUs

Zone-redundant and zonal gateways are available as gateway SKUs. There is a new virtual network gateway SKUs in Azure AZ regions. These SKUs are like the corresponding existing SKUs for ExpressRoute and VPN Gateway, except that they are specific to zone-redundant and zonal gateways. You can identify these SKUs by the "AZ" in the SKU name.

Public IP SKUs

Zone-redundant gateways and zonal gateways both rely on the Azure public IP resource Standard SKU. The configuration of the Azure public IP resource determines whether the gateway that you deploy is zone-redundant, or zonal. If you create a public IP resource with a Basic SKU, the gateway will not have any zone redundancy, and the gateway resources will be regional.

Configure a Site-to-Site VPN as a failover path for ExpressRoute
The ExpressRoute circuit is always the primary link. Data flows through the Site-to-Site VPN path only if the ExpressRoute circuit fails. To avoid asymmetrical routing, your local network configuration should also prefer the ExpressRoute circuit over the Site-to-Site VPN. You can prefer the ExpressRoute path by setting higher local preference for the routes received the ExpressRoute.

Global connectivity with ExpressRoute Premium, Local connectivity with ExpressRoute Local, Across on-premises connectivity with ExpressRoute Global Reach

ER creation steps -
	1) Create VNET
	2) Create GatewaySubnet
	3) Create virtual network gateway with Gateway type as ER
Provision ER
	1) Networking - ER - create
	2) Basic tab - Name - RG etc
	3) On the configuration tab select port type - provider, create new, Provider name, peering location, bandW, SKU,
Billing model, 
	4) Retrieve service key from ER - ER circuits - overview 
	5) Hand over the service key to the provider

Configure peering for an ExpressRoute deployment
You can configure private peering and Microsoft peering for an ExpressRoute circuit. Peering's can be configured in any order you choose. However, you must make sure that you complete the configuration of each peering one at a time.
You must have an active ExpressRoute circuit. Have the circuit enabled by your connectivity provider before you continue. To configure peering(s), the ExpressRoute circuit must be in a provisioned and enabled state For L3 your SP configures and manages routing for you. Each peering requires separate BGP sessions (one pair for each peering type). The BGP session pairs provide a highly available link. If you are connecting through layer 2 connectivity providers, you are responsible for configuring and managing routing.


About route filters

When Microsoft peering gets configured on your ExpressRoute circuit, the Microsoft Edge routers establish a pair of BGP sessions with your edge routers through your connectivity provider. No routes are advertised to your network. To enable route advertisements to your network, you must associate a route filter.

A route filter lets you identify services you want to consume through your ExpressRoute circuit's Microsoft peering. 


Create a route filter and a filter rule
A route filter can have only one rule, and the rule must be of type 'Allow'. This rule can have a list of BGP community values associated with it.

Select Create a resource then search for Route filter
Select the services you want to connect to from the drop-down list and save the rule when done.
Attach the route filter to an ExpressRoute circuit

Add a VPN to an ExpressRoute deployment
You can use Microsoft peering to establish a site-to-site IPsec/IKE VPN tunnel between your selected on-premises networks and Azure VNets. Configuring a secure tunnel over ExpressRoute allows for data exchange with confidentiality, anti-replay, authenticity, and integrity.

Choose when to use ExpressRoute global reach
ExpressRoute Global Reach is designed to complement your service provider’s WAN implementation and connect your branch offices across the world. For example, if your service provider primarily operates in the United States and has linked all your branches in the U.S., but the service provider does not operate in Japan and Hong Kong SAR, with ExpressRoute Global Reach you can work with a local service provider and Microsoft will connect your branches there to the ones in the U.S. using ExpressRoute and the Microsoft global network.

On the Add Global Reach configuration page, give a name to this configuration. Select the ExpressRoute circuit you want to connect this circuit to and enter in a /29 IPv4 for the Global Reach subnet. Azure uses IP addresses in this subnet to establish connectivity between the two ExpressRoute circuits. Do not use the addresses in this subnet in your Azure virtual networks, or in your on-premises network. Select Add to add the circuit to the private peering configuration.


Improve data path performance between networks with ExpressRoute FastPath
200 XP
10 minutes
ExpressRoute virtual network gateway is designed to exchange network routes and route network traffic. FastPath is designed to improve the data path performance between your on-premises network and your virtual network. When enabled, FastPath sends network traffic directly to virtual machines in the virtual network, bypassing the gateway.

Circuits

FastPath is available on all ExpressRoute circuits.

Gateways

FastPath still requires a virtual network gateway to be created to exchange routes between virtual network and on-premises network.

](Journey/002/Readme.md)




- [ ] ☁️ 3 > [](Journey/003/Readme.md)
April 20th. LERNING BICEP

Type 
Install extension for bicep in VB
Create a file name ending with bicep
Res-resource (eg storage, compute, app or app service) to get suggestion and about the resource creation
Once populated change the symbolic name, resource name, location, SKU, type etc.
When changing kind of SKU delete existing one and type control space to get list of suggestion

To add some properties -
Type property after the resource bracket and get suggestion.


DependOn eg of webAppName
"dependsOn":[
	"[parameters('appServicePlanName')]"
	
Web app cannot be deployed without app service plan and you can verify with visualize (eye). BICEP DOES NOT REQUIRE DEPENDSON property of ARM IT picks up from resource properties
Eg serverFarmID: appServicePlan.id

Parent child resources -
Using parent keyword useful for separate looks.
OR 
Nested child resources under curly bracket


VARIABLES and FUNCTIONs -

String interpolation over concatination with unique string function

Eg 
Var vmname = concat('vm',uniqueString(resourceGroup().id) 
Suggested and corrected to
Var vmnware = 'vm${uniqueString(resourceGroup().id)}'

Once the VM name variable is created we can create additional string interpolation for public IP and NIC name with Vmname eg
NIC
Name =  'NIC$(VMName)'

Resource publicIP
Name = 'PIP$(vmname)'

SECURESTRING parameter for password
Param vmUserName string  = 'pcadmin'

@secure()
Param vmPass string

Other decorators (@allowed values) eg

@allowed(
	'windowss'
	'linux'
	])
	Param winOrLin string ='windows'
	
Var image = {
 windows: {
	Publisher:
	Offer:
	Sku:
	Version
}
 Linux: {
	Publisher:
	Offer:
	Sku:
	Version
 }
}






Another good example of decorator with condition . @allowd([
	'prod'
	'dev'
	])
	
	


da

Var vmsize = (env == 'prod') ? 'Standard_D2s_V3' : 'Standard B2s'
And now on the resource definition change the Vmsize with the var vmsize

Now create seprate parameter file with at least the default values WHICH IS IN JSON FORMAT SAME AS ARM template.


If then with Boolean could be tricky as it requires empty response to NO response .
If VN param is new then only it will be deployed. Better than using boolean which does not respond on value.



Resource virtual network 'microsoft.network/virtualnetwo@1111' = if(newOrExistingVnet == 'new') {
Name: xx
Location : ;ocatopn
Properties: {
 addressspace: {
 addressprefixes : {
Fvvf




Loop eg of Data disk

Param datadisCount int

Datadisks: [for I in range(i,dataDiskCount):{
createOtion: 'Empty'
Lun: I
diskSizeGB: 100
Name: '$(vmnamme)--datadisk${i}'
datadisk

Easier to start with 1 THEN 0


- [ ] ☁️ 4 > [](Journey/004/Readme.md)
MAY 13, 22 Azure PAAS learnign code for configuribng Web app with SQL

Startup.cs

    // ADDED BY PC With  CONITIONAL ACCESS WHICH FIRST FINDS THE AZURE DB COPY AS PRIMARY AND FALLS BACK ON LOCAL DB ONLY IF AZ DB NOT FOUND, AZURE WEB ANYWAYS CANNOT FALL BACK ON LOCAL DB
            if (Environment.GetEnvironmentVariable("ASPNETCORE_ENVIRONMENT") == "Production")
            {
                services.AddDbContext<AdventureWorksLT2016Context>(options => options.UseSqlServer(Configuration.GetConnectionString("AdventureWorksDbContextAzure")));
            }
            else
            {
                services.AddDbContext<AdventureWorksLT2016Context>(options => options.UseSqlServer(Configuration.GetConnectionString("AdventureWorksDbContext")));

            }
            services.Configure<DbConnectionSettings>(Configuration.GetSection("ConnectionStrings"));

           services.AddApplicationInsightsTelemetry(Configuration["APPINSIGHTS_CONNECTIONSTRING"]);



LAYOUT.cshtml

  <li class="nav-item">
                            <a class="nav-link text-dark" asp-area="" asp-page="/Products/Index">Products</a>




ConfigurationSettings.cs

namespace MvcProductCore
{
    //replaced by PC from configuration setttings
    public class DbConnectionSettings
    {
        public string AdventureDbWorksContext { get; set; }
       // Added by  PC for Azure 
        public string AdventureDbWorksContextAzure { get; set; }
    }

ApoSettings.Json


   //  ADDDED BY PC FOR LOCAL DB 
    "AdventureWorksDbContext": "Server=(localdb)\\mssqllocaldb;Database=AdventureWorksLT2016;Trusted_Connection=True;MultipleActiveResultSets=true"
  },
  "ApplicationInsights": {
    "ConnectionString": "InstrumentationKey=14146c59-232a-4ca4-9e22-521be1f1f82f;IngestionEndpoint=https://eastus-0.in.applicationinsights.azure.com/;LiveEndpoint=https://eastus.livediagnostics.monitor.azure.com/"
  }
}




- [ ] ☁️ 5 > [](Journey/005/Readme.md)

May23, Configuring COSMOS DB with VS 19 using nuget packages not successful 

				
Deployed Cosmos	Deployed with core SQL small change from the instruction to Azure. Choices for core SQ: and other DB right at the begingin			
Nuget package	Deployed Microsoft.Azure.Cosmos latest stable 3.27.0 over 3.16			
	Models folder, select Add > Class.			
	5. In Add New Item, name your new class Feedback.cs ..
	
	using System.ComponentModel.DataAnnotations; 
	using Newtonsoft.Json
	
	    [Key]
	        [JsonProperty(PropertyName = "id")]
	        public string id { get; set; }
	        [JsonProperty(PropertyName = "firstname")]
	        public string FirstName { get; set; }
	        [JsonProperty(PropertyName = "lastname")]
	        public string LastName { get; set; }
	        [JsonProperty(PropertyName = "emailaddress")]
	        public string EmailAddress { get; set; }
	        [JsonProperty(PropertyName = "comments")]
	        public string Comments { get; set; }
	
@ project level	Added new folder SERVICES			
	Added new class CosmosDBService.cs under the Folder
	Added one more service ICosmosDBService.cs . 
	
	s CosmosDBService.cs 
	
	using System.Collections.Generic;
	using System.Linq;
	using System.Threading.Tasks;
	using MvcProductCore.Models;
	using Microsoft.Azure.Cosmos;
	using Microsoft.Azure.Cosmos.Fluent;
	using Microsoft.Extensions.Configuration;
	
	namespace MvcProductCore.Services
	{
	    public class CosmosDBService
	    {
	        private Container _container;
	        public CosmosDbService(
	            CosmosClient dbClient,
	            string databaseName,
	            string containerName)
	        {
	            this._container = dbClient.GetContainer(databaseName, containerName);
	        }
	        public async Task AddItemAsync(Feedback feedback)
	        {
	            await this._container.CreateItemAsync<Feedback>(feedback, new PartitionKey(feedback.id));
	
	        }
	        public async Task DeleteItemAsync(string id)
	        {
	            await this._container.DeleteItemAsync<Feedback>(id, new PartitionKey(id));
	        }
	
	        public async Task<Feedback> GetItemAsync(string id)
	        {
	            try
	            {
	                ItemResponse<Feedback> response = await this._container.ReadItemAsync<Feedback>(id, new PartitionKey(id));
	                return response.Resource;
	            }
	            catch (CosmosException ex) when (ex.StatusCode == System.Net.HttpStatusCode.NotFound)
	            {
	                return null;
	            }
	           }
	        public async Task<IEnumerable<Feedback>> GetItemsAsync(string queryString)
	        {
	            var query = this._container.GetItemQueryIterator<Feedback>(new QueryDefinition(queryString));
	            List<Feedback> results = new List<Feedback>();
	            while (query.HasMoreResults)
	            {
	                var response = await query.ReadNextAsync();
	
	                results.AddRange(response.ToList());
	
	            }
	            return results;
	        }
	        public async Task UpdateItemAsync(string id, Feedback feedback)
	        {
	            await this._container.UpsertItemAsync<Feedback>(feedback, new PartitionKey(id));
	        }
	
	    }
	
	}
	
	
	ICosmosDBServices
	using System.Collections.Generic;
	using System.Linq;
	using System.Threading.Tasks;
	using MvcProductCore.Models;
	
	namespace MvcProductCore.Services
	{
	    public class ICosmosDBService
	    {
	        Task<IEnumerable<Feedback>> GetItemsAsync(string query);
	        Task<Feedback> GetItemAsync(string id);
	        Task AddItemAsync(Feedback feedback);
	        Task UpdateItemAsync(string id, Feedback feedback);
	        Task DeleteItemAsync(string id);
	    }
	}
	
	Note: We have created only two views but here we are adding other functionality. I (Intellisense error on all three aboive
	Starup.cs  (updated			
	
	Updated (clientsettings.json)			
	Intelli Fixes			
	On 
	IcosmosDBServices.sc
	
	FROM
	  Task<IEnumerable<Feedback>> GetItemsAsync(string query);
	
	TO 
	Task<Feedback> GetItemAsync(string id);



- [ ] ☁️ 6 > [NOT working with description](Journey/006/Readme.md)

May 18 - AZ400 learning CI pipeline


Built CI using the Azure github lab 

AZ400-DesigningandImplementingMicrosoftDevOpsSolutions/AZ400_M03_Enabling_Continuous_Integration_with_Azure_Pipelines.md at master · MicrosoftLearning/AZ400-DesigningandImplementingMicrosoftDevOpsSolutions (github.com)

Followed the instruction to create new Project "PartsUnlimited " using the Azure DevopsGenerator and template for thePartsUnlimited.

From the pipleline disabled the CI checkbox from the existing pipeline that was built on the template using the TASK tab and Saved the pipeline changes.

Created a new Pipeline using the classic editor while keeping "PartsUnlimited " as the master branch repo. Selected ASP.NET as source template and applied the template to the build definition.

From the task disabled the Test Assembly 
From the Triggered tab enabled CI checked. Saved, queued and RAN the Pipeline 

- [ ] ☁️ 7 > [](Journey/007/Readme.md)

May 18th AZ400 deploying self hosted agent 

I started this lab thinking it will be generating VM in Azure for with self-hosted agent and I did not see any VM.  I though may it was unable to create VM on the release pipeline as the lab followed PAT authentication instead of SP. I created SP on Devops and allowed contributor role on Azure and it still failed after that when I reviewed the lab it was about deploying agent but not hosted VM with the agent on Azure.


Here is the github link

AZ400-DesigningandImplementingMicrosoftDevOpsSolutions/AZ400_M03_Configuring_Agent_Pools_and_Understanding_Pipeline_Styles.md at master · MicrosoftLearning/AZ400-DesigningandImplementingMicrosoftDevOpsSolutions (github.com)



Followed the instruction to create new Project "PartsUnlimited " using the Azure DevopsGenerator and template for thePartsUnlimited.

Created a new pipeline based on the code repo generated by the Devops generator.

1) Created PAT from devops user settings.
	2) From the Org Settings - Pipelines - Added the self-agent pool name AZ400SHA-pool.
	3) From the new agent pool create a new agent.
	4) Download the zip file with the PowerShell instruction to deploy
	5) Followed the PowerShell instruction verbatim to create a directory and extracting file on that directory and running the extracted script and accepting the prompt generated by the script.
	6) Verified the status of new Agents on Agent tab of the new Agent pool.
	7) Selected the pipeline for PartsUnlimited edited the YAML pipeline to replace the default target agent VMImage: windows-2019 WITH name: az400m05l05a-pool.
	8) Clicked on settings above the target name on the YAML file to change the version of the nuget to 4.0.0. Saved and run the pipeline job.
	



- [ ] ☁️ 8 > [](Journey/008/Readme.md)

May 18th GitHub Actions by using DevOps Starter

	1) Created DevOps starter with GiTHUB as source.
	2) Authorize GitHub Actionsaz400m08l01
	3) Created the Gibhub repo name "az400m08l01"
	4) On DevOps starter Reviewed GITHub workflow page and Azure resources page and the status
	5) From DevOps starter selected repo link to switch to Github to view the repo.
	6) View build, deploy, fucntional test and commit.
	7) Made the changes to idex.cshtml by adding <div class="description line-1"> GitHub Workflow has been successfully updated</div>on the line 19th
	8) Commit failed after that with error on <. Tried removing < and adding to line 20 instead and also added cli version on YAML deployment task for the Azure ARM deployment task.
	9) Remove both changes and ran commit again and it was successful again
Not sure if anyone have had same issue with this lab
	
	


- [ ] ☁️ 9 > [](Journey/009/Readme.md)

May 18th  Lab 07: Integrating External Source Control with Azure Pipelines

https://github.com/MicrosoftLearning/AZ400-DesigningandImplementingMicrosoftDevOpsSolutions/blob/master/Instructions/Labs/AZ400_M03_Integrating_External_Source_Control_with_Azure_Pipelines.md#lab-07-integrating-external-source-control-with-azure-pipelines




[![Build Status](https://dev.azure.com/pchettri52022/Integrating%20External%20Source%20Control/_apis/build/status/pchettri3.calculator?branchName=master)](https://dev.azure.com/pchettri52022/Integrating%20External%20Source%20Control/_build/latest?definitionId=8&branchName=master)



Error: Resource 'PU132777864-Canary' doesn't exist. Resource should exist before deployment.

From <https://dev.azure.com/pchettri52022/Controlling%20Deployments%20using%20Release%20Gates/_releaseProgress?_a=release-environment-logs&releaseId=2&environmentId=3#> 



- [ ] ☁️ 10 > [](Journey/010/Readme.md)

## Walking down the road

- [ ] ☁️ 11 > [](Journey/011/Readme.md)
- [ ] ☁️ 12 > [](Journey/012/Readme.md)
- [ ] ☁️ 13 > [](Journey/013/Readme.md)
- [ ] ☁️ 14 > [](Journey/014/Readme.md)
- [ ] ☁️ 15 > [](Journey/015/Readme.md)
- [ ] ☁️ 16 > [](Journey/016/Readme.md)
- [ ] ☁️ 17 > [](Journey/017/Readme.md)
- [ ] ☁️ 18 > [](Journey/018/Readme.md)
- [ ] ☁️ 19 > [](Journey/019/Readme.md)
- [ ] ☁️ 20 > [](Journey/020/Readme.md)

## Crossing the bridge

- [ ] ☁️ 21 > [](Journey/021/Readme.md)
- [ ] ☁️ 22 > [](Journey/022/Readme.md)
- [ ] ☁️ 23 > [](Journey/023/Readme.md)
- [ ] ☁️ 24 > [](Journey/024/Readme.md)
- [ ] ☁️ 25 > [](Journey/025/Readme.md)
- [ ] ☁️ 26 > [](Journey/026/Readme.md)
- [ ] ☁️ 27 > [](Journey/027/Readme.md)
- [ ] ☁️ 28 > [](Journey/028/Readme.md)
- [ ] ☁️ 29 > [](Journey/029/Readme.md)
- [ ] ☁️ 30 > [](Journey/030/Readme.md)

## Into the bushy, thorny forest

- [ ] ☁️ 31 > [](Journey/031/Readme.md)
- [ ] ☁️ 32 > [](Journey/032/Readme.md)
- [ ] ☁️ 33 > [](Journey/033/Readme.md)
- [ ] ☁️ 34 > [](Journey/034/Readme.md)
- [ ] ☁️ 35 > [](Journey/035/Readme.md)
- [ ] ☁️ 36 > [](Journey/036/Readme.md)
- [ ] ☁️ 37 > [](Journey/037/Readme.md)
- [ ] ☁️ 38 > [](Journey/038/Readme.md)
- [ ] ☁️ 39 > [](Journey/039/Readme.md)
- [ ] ☁️ 40 > [](Journey/040/Readme.md)

## Trekking the dunes

- [ ] ☁️ 41 > [](Journey/041/Readme.md)
- [ ] ☁️ 42 > [](Journey/042/Readme.md)
- [ ] ☁️ 43 > [](Journey/043/Readme.md)
- [ ] ☁️ 44 > [](Journey/044/Readme.md)
- [ ] ☁️ 45 > [](Journey/045/Readme.md)
- [ ] ☁️ 46 > [](Journey/046/Readme.md)
- [ ] ☁️ 47 > [](Journey/047/Readme.md)
- [ ] ☁️ 48 > [](Journey/048/Readme.md)
- [ ] ☁️ 49 > [](Journey/049/Readme.md)
- [ ] ☁️ 50 > [](Journey/050/Readme.md)

## Winding through the canyons

- [ ] ☁️ 51 > [](Journey/051/Readme.md)
- [ ] ☁️ 52 > [](Journey/052/Readme.md)
- [ ] ☁️ 53 > [](Journey/053/Readme.md)
- [ ] ☁️ 54 > [](Journey/054/Readme.md)
- [ ] ☁️ 55 > [](Journey/055/Readme.md)
- [ ] ☁️ 56 > [](Journey/056/Readme.md)
- [ ] ☁️ 57 > [](Journey/057/Readme.md)
- [ ] ☁️ 58 > [](Journey/058/Readme.md)
- [ ] ☁️ 59 > [](Journey/059/Readme.md)
- [ ] ☁️ 60 > [](Journey/060/Readme.md)

## Stumbling through the caves

- [ ] ☁️ 61 > [](Journey/061/Readme.md)
- [ ] ☁️ 62 > [](Journey/062/Readme.md)
- [ ] ☁️ 63 > [](Journey/063/Readme.md)
- [ ] ☁️ 64 > [](Journey/064/Readme.md)
- [ ] ☁️ 65 > [](Journey/065/Readme.md)
- [ ] ☁️ 66 > [](Journey/066/Readme.md)
- [ ] ☁️ 67 > [](Journey/067/Readme.md)
- [ ] ☁️ 68 > [](Journey/068/Readme.md)
- [ ] ☁️ 69 > [](Journey/069/Readme.md)
- [ ] ☁️ 70 > [](Journey/070/Readme.md)

## Resting at the Lagoon

- [ ] ☁️ 71 > [](Journey/071/Readme.md)
- [ ] ☁️ 72 > [](Journey/072/Readme.md)
- [ ] ☁️ 73 > [](Journey/073/Readme.md)
- [ ] ☁️ 74 > [](Journey/074/Readme.md)
- [ ] ☁️ 75 > [](Journey/075/Readme.md)
- [ ] ☁️ 76 > [](Journey/076/Readme.md)
- [ ] ☁️ 77 > [](Journey/077/Readme.md)
- [ ] ☁️ 78 > [](Journey/078/Readme.md)
- [ ] ☁️ 79 > [](Journey/079/Readme.md)
- [ ] ☁️ 80 > [](Journey/080/Readme.md)

## Up into the mountains

- [ ] ☁️ 81 > [](Journey/081/Readme.md)
- [ ] ☁️ 82 > [](Journey/082/Readme.md)
- [ ] ☁️ 83 > [](Journey/083/Readme.md)
- [ ] ☁️ 84 > [](Journey/084/Readme.md)
- [ ] ☁️ 85 > [](Journey/085/Readme.md)
- [ ] ☁️ 86 > [](Journey/086/Readme.md)
- [ ] ☁️ 87 > [](Journey/087/Readme.md)
- [ ] ☁️ 88 > [](Journey/088/Readme.md)
- [ ] ☁️ 89 > [](Journey/089/Readme.md)
- [ ] ☁️ 90 > [](Journey/090/Readme.md)

## Into the sky to touch the cloud!

- [ ] ☁️ 91 > [](Journey/091/Readme.md)
- [ ] ☁️ 92 > [](Journey/092/Readme.md)
- [ ] ☁️ 93 > [](Journey/093/Readme.md)
- [ ] ☁️ 94 > [](Journey/094/Readme.md)
- [ ] ☁️ 95 > [](Journey/095/Readme.md)
- [ ] ☁️ 96 > [](Journey/096/Readme.md)
- [ ] ☁️ 97 > [](Journey/097/Readme.md)
- [ ] ☁️ 98 > [](Journey/098/Readme.md)
- [ ] ☁️ 99 > [](Journey/099/Readme.md)
- [ ] ☁️ 100 > [](Journey/100/Readme.md)
