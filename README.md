# Step-by-Step AKS Workflow - EKS to AKS Considerations
#### [Made by Rick Kemery with Scribe](https://scribehow.com/shared/Step-by-Step_AKS_Workflow_-_EKS_to_AKS_Considerations__O2mSEOO4Q0mPy_VWTijcBw)
Create an AKS cluster in Azure and learn more about the workflow from start to finish - along with considerations when migrating from EKS workloads to AKS!

**1. Navigate to https://portal.azure.com/#home**

**2. Click the "Search resources, services, and docs (G+/)" field.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2022-12-07/d3812d67-6f4b-45d3-b1d5-59d5ea0298ca/ascreenshot.jpeg?tl_px=1034,0&amp;br_px=1780,420&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=262,-4)

**3. Type "aks"**

**4. Click "Kubernetes services"**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2022-12-07/7962323f-d84d-498a-952f-731b979e15c4/ascreenshot.jpeg?tl_px=1468,0&amp;br_px=2214,420&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=262,112)

**5. Click this icon to begin creating a Kubernetes service deployment.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2022-12-07/287e77d3-ab99-4540-92bb-b68f9f9be54e/ascreenshot.jpeg?tl_px=1360,380&amp;br_px=2106,800&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=262,139)

**6. Click "Create a Kubernetes cluster" to begin the workflow.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2022-12-07/afc99a4f-015e-4b61-a1b5-f37c88af6afb/ascreenshot.jpeg?tl_px=1366,415&amp;br_px=2112,835&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=262,139)

**7. Click "(New) Resource group" for the AKS deployment; both AWS and Azure have the concept of Resource Groups; some key items are that one Azure resource is always associated with one resource group and it can be organized via tags. You can also manage them with the Web Interface (Azure Portal), REST API, Command Line, PowerShell, or ARM Templates.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/dd354c4e-347c-4668-a25b-b511f32ceaf8/user_cropped_screenshot.jpeg?tl_px=14,206&amp;br_px=760,626&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=262,139)

**8. I have an example Resource Group created named "rk-aks-demo" that I will use.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/a2bea908-b304-4cf9-815f-c34a468f38e7/user_cropped_screenshot.jpeg?tl_px=88,372&amp;br_px=834,792&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=262,139)

**9. For demo purposes, we will use the "Dev/Test" Cluster preset configuration. One advantage in this workflow compared to AWS is that we offer several presets. These are 5 levels of presets that offer different advantages for cost and features/workloads that can get you started quick.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/9d09b52d-0025-4c0f-83f6-3a042328cba1/user_cropped_screenshot.jpeg?tl_px=103,253&amp;br_px=849,673&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=262,139)

**10. For demo purposes and Dev/Test environment, click "Best for experimenting with AKS or deploying a test app." Dev/Test will set system node pool size to B4ms shape with Cluster Autoscaling and 99.5% API server availability.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/eb36ddac-329f-49ed-a066-502366a620e3/user_cropped_screenshot.jpeg?tl_px=143,428&amp;br_px=889,848&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=262,139)

**11. Create a name for your cluster - click the "Kubernetes cluster name" field and enter it.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/b9527355-54f5-4720-ba2a-518f0433cdc9/user_cropped_screenshot.jpeg?tl_px=98,398&amp;br_px=844,818&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=262,139)

**12. Since am I close to the Central US Azure datacenter, I chose it as my Region. Click "(US) Central US"**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/154170d5-01f7-4a38-a88e-ebb2f0ee2f65/user_cropped_screenshot.jpeg?tl_px=87,434&amp;br_px=833,854&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=262,139)

**13. During setup of AKS, it is important to understand production workloads and plan for resilience against datacenter failures. AKS clusters that are deployed using availability zones can distribute nodes across multiple zones within a single region - improving cluster availability. This is also the recommended approach when considering migrating from Amazon EKS to AKS.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/1a3e07f9-8e3f-4249-8183-ac7715441bce/user_cropped_screenshot.jpeg?tl_px=66,479&amp;br_px=812,899&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=262,139)

**14. Description of Availability Zones during setup.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/03064f47-ea02-4809-be14-9bf6d8a1f1ca/user_cropped_screenshot.jpeg?tl_px=0,459&amp;br_px=746,879&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=87,139)

**15. We will use the default k8s version selected. Note this may be different depending on the time you create the cluster as these options change as new versions get released. Click the version with "(default)" in it. You have the option to move to older and new (preview) releases right from the start. When migrating from EKS to AKS it is important to ensure your target k8s version is within the supported window for AKS.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/5c612c13-b0be-4386-9717-bab1ee9a3877/user_cropped_screenshot.jpeg?tl_px=0,516&amp;br_px=746,936&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=261,139)

**16. Since this is a demo, we can select 99.5% API server availability.  API server availability is an uptime service level agreement that guarantees a Kubernetes API server uptime of 99.95% clusters with one or more availability zones and 99.9% for all other clusters. **

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/1160e10e-9f57-45e1-a4c6-abdd66173237/user_cropped_screenshot.jpeg?tl_px=0,557&amp;br_px=746,977&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=106,139)

**17. In continuation of selecting an appropriate k8s version in line with our considerations from EKS to AKS, we can also select automatic upgrades. "Enabled with path (recommended)" will update the cluster to the latest patch version within the set minor version. We also have the option to select stable, rapid, node image, and disabled - depending on our workloads on EKS we might select stable for production workloads.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/d603857e-844f-41e8-ba98-402bc318d92d/user_cropped_screenshot.jpeg?tl_px=49,13&amp;br_px=795,433&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=300,139)

**18. Sizing the k8s nodes is important when considering EKS to AKS. The types of workloads and their usage will influence the choice of how many nodes and what node size we use for the cluster. It is also important to consider valid quotas for the migration. You should verify that your quotas and limits are sufficient for these resources and if necessary, request and increase in vCPU quota.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/c5619d52-52bd-4158-aa41-8ba9db1dc174/user_cropped_screenshot.jpeg?tl_px=0,746&amp;br_px=746,1166&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=64,139)

**19. We can also select the min and max of nodes to use for autoscaling. If your EKS cluster uses autoscaling and was engineered for high availability and business continuity with respect to elasticity - then the number of nodes is important.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/c25c709a-648d-4951-bdd4-01694ca95431/user_cropped_screenshot.jpeg?tl_px=0,773&amp;br_px=746,1193&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=210,265)

**20. Go to the next page and click "Next: Node pools >" Here we can configure additional node pools to handle a variety of workloads and in contrast to some of the obscurity in EKS, we can enable "virtual nodes" right from the start for Azure Container Instance fast burst scaling. We can also select the type of node pool OS disk encryption - important if you are planning to migrate from EKS with your own keys.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/64088a39-c080-466d-a452-6b2eea1a84b8/user_cropped_screenshot.jpeg?tl_px=0,759&amp;br_px=746,1179&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=156,273)

**21. Next, we can move to Access. Click "Next : Access >"**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/1541f5f1-ea00-4cf4-8c4b-dd480782504e/user_cropped_screenshot.jpeg?tl_px=0,702&amp;br_px=746,1122&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=148,268)

**22. AKS setup allows for 3 types of authentication and authorization: Local accounts with k8s RBAC, Azure AD authentication with k8s RBAC, and Azure AD authentication with Azure RBAC. One strength of AKS is its tight coupling with Azure AD to use Azure role assignments for authorization checks on the cluster.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/19a4f6c7-3689-4fb3-8781-2a9b026cd3e4/user_cropped_screenshot.jpeg?tl_px=24,131&amp;br_px=770,551&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=262,139)

**23. Next, we will go to the Networking overview. Click "Next : Networking >"**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/7d987604-c61c-4813-9299-08d69607514d/user_cropped_screenshot.jpeg?tl_px=0,760&amp;br_px=746,1180&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=182,265)

**24. Networking is very important when considering migrating from EKS to AKS. It is important to inventory the range of services and applications that uses them in the EKS cluster and then follow best practices for downtime handling. You might typically migrate over time rather than all at once, meaning old and new enviroments might need to communicate over the network. If an application previously used ClusterIP services to communicate might need to be exposed as LoadBalancer type and secured appropriately after the migration. Ideally, you want to point clients to new services that are running on AKS and we recommend that you redirect traffic by updating DNS to point to the Load Balancing sitting in front of your AKS cluster - Azure Traffic Manager can direct customers to the desired k8s cluster and application instance.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/ead1134c-1cad-42bb-9df0-4b9de797c77b/user_cropped_screenshot.jpeg?tl_px=0,166&amp;br_px=746,586&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=201,139)

**25. In the network section, we can define and create a new virtual network. Both Azure VNet and AWS VPC segregate networks with subnets. Azure VNet assigns resources connected and deployed to the VNet a private IP address for the CIDR block specified and the smallest subnet supported is /29 and largest is a /8. Record the CIDR block range you need when migrating from EKS to AKS for k8s services and and the cluster as you do not want to experience IP exhaustion and also want to be able to scale accordingly.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/de2f0e67-6606-4bd7-942a-97c497417fe0/user_cropped_screenshot.jpeg?tl_px=0,270&amp;br_px=746,690&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=88,139)

**26. The k8s service address range description.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/55f971c5-1d7c-48e6-a2ca-cd822a0bbc7a/user_cropped_screenshot.jpeg?tl_px=0,350&amp;br_px=746,770&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=164,139)

**27. The k8s DNS service IP address description.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/c082211d-45de-46cc-a02f-1dc74783ce0e/user_cropped_screenshot.jpeg?tl_px=0,410&amp;br_px=746,830&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=173,139)

**28. You can also change the network for the Docker Bridge address - Click "Docker Bridge address"**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/09059058-3cc5-4c23-9a0a-53e03b49a46d/user_cropped_screenshot.jpeg?tl_px=0,463&amp;br_px=746,883&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=114,139)

**29. Description for DNS name prefix for the hosted k8s API server FQDN - important to consider when migrating as this will be used to connect to when managing containers after creating the cluster.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/e57792e1-fd27-424b-b576-aca2374f0ccf/user_cropped_screenshot.jpeg?tl_px=0,495&amp;br_px=746,915&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=94,139)

**30. Enabling "HTTP Application Routing" will configure an ingress controller in your AKS cluster and as applications are deployed, the ingress controller will create publicly accessible DNS names for your application endpoints. Consider what this might mean for your applications as your migrate over - how many and what needs to be publicly available via ingress and what type of configurations are currently in place that need to be done in the new cluster.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/9652512b-a935-4357-9579-7c92f8e2b959/user_cropped_screenshot.jpeg?tl_px=0,773&amp;br_px=746,1193&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=78,139)

**31. In this section, we can select the type of network policy structure for the k8s cluster. We can use Calico or Azure - Azure being one of the key differentiators out of the box vs EKS. Azure allows for Azure Network Policies via Azure Network Policy Manager (NPM) which uses IPTables for Linux and Host Network Service (HNS) ACLPolicies for Windows.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/f4b8518a-0f12-43b7-ba03-54322c8ef96a/user_cropped_screenshot.jpeg?tl_px=45,686&amp;br_px=791,1106&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=262,345)

**32. Click "Next : Integrations >"**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/14a323ce-5a99-4817-af92-a82fc9633271/user_cropped_screenshot.jpeg?tl_px=0,808&amp;br_px=746,1228&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=149,270)

**33. Out of the box, we can enable Microsoft Defender for Cloud which provides unified security management and threat protection across the workloads - importantly when migrating production workloads we want to consider the security policies and protection against threats as we build in AKS. Using Defender backed with Azure Monitor and Azure Policy allows for threat protection, container insights, and at-scale enforcements and safeguards for AKS clusters in a centralized, consistent manner through Azure Policy.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/caf193b2-1b87-40ae-a0a5-cd0c00586a0d/user_cropped_screenshot.jpeg?tl_px=0,247&amp;br_px=746,667&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=245,139)

**34. When migrating from EKS to AKS, we likely will have a set of images that are pre-built or need built for the new cluster; we can use tools like Azure Migrate to help with that along with connecting the AKS cluster to Azure Container Registry to store and use these images.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/a7367d84-aad1-4d1a-a8fb-5806040ec288/user_cropped_screenshot.jpeg?tl_px=0,273&amp;br_px=746,693&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=231,139)

**35. Click "Next : Advanced >"**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/ddaf52b3-3862-439c-bc61-0c625403a838/user_cropped_screenshot.jpeg?tl_px=0,761&amp;br_px=746,1181&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=152,268)

**36. When migrating from EKS to AKS, it is important to know the type of data persistence and where the new data will be stored. When we create AKS cluster we have the option to enable secret store CSI driver which also allows us to integrate Azure Key Vault secrets. Ideally, when we migrate persistent volumes, we want to quiesce writes to the application, take snapshosts of the disks, create new managed disks from the snapshots, create persistent volumes in AKS, update the pod spec to use existing volumes rather than static provisioning, then deploy the application to AKS, validate it and point live traffic to the new cluster. You can use tools like Azure CLI Disk Copy extension and Azure Kube CLI extension to migrate volumes between k8s clusters.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/cb59ac0b-8abd-4610-947e-e20fbe0fb1ac/user_cropped_screenshot.jpeg?tl_px=0,0&amp;br_px=746,420&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=195,120)

**37. Click "Next : Tags >" here we can tag the AKS cluster for certain things like environment.**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/943bab8d-8f64-4431-b09c-55755bbd47af/user_cropped_screenshot.jpeg?tl_px=0,754&amp;br_px=746,1174&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=138,270)

**38. We're ready to create our AKS cluster! Click "Next : Review + create >"**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/223d295e-de88-4aff-bbdd-914161765af4/user_cropped_screenshot.jpeg?tl_px=0,769&amp;br_px=746,1189&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=187,267)

**39. After the cluster has been provisioned, we can connect to it by clicking "Connect to cluster"**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/b306f41a-156b-4c56-b9bf-caa784d28a25/user_cropped_screenshot.jpeg?tl_px=19,292&amp;br_px=765,712&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=262,139)

**40. We can quickly get a snapshot of the current environment using Cloud Shell - Click "Open Cloud Shell" - from here it gives us all the commands to run and even sets the accout and credentials for us when we open Cloud Shell - then from here we can get deployments and list namespaces and being our EKS to AKS migration!**

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2023-02-01/c31de1a4-49ec-452d-ae01-5ca5365792f0/user_cropped_screenshot.jpeg?tl_px=0,0&amp;br_px=746,420&amp;sharp=0.8&amp;width=560&amp;wat_scale=50&amp;wat=1&amp;wat_opacity=0.7&amp;wat_gravity=northwest&amp;wat_url=https://colony-labs-public.s3.us-east-2.amazonaws.com/images/watermarks/watermark_default.png&amp;wat_pad=57,130)
#### [Made with Scribe](https://scribehow.com/shared/Step-by-Step_AKS_Workflow_-_EKS_to_AKS_Considerations__O2mSEOO4Q0mPy_VWTijcBw)


