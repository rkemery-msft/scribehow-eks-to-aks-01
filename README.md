# Step-by-Step AKS Workflow - EKS to AKS Considerations
#### [Made by Rick Kemery with Scribe](https://scribehow.com/shared/Step-by-Step_AKS_Workflow_-_EKS_to_AKS_Considerations__O2mSEOO4Q0mPy_VWTijcBw)
Create an AKS cluster in Azure and learn more about the workflow from start to finish - along with considerations when migrating from EKS workloads to AKS!

**1. Navigate to https://portal.azure.com/#home**

**2. Click the "Search resources, services, and docs (G+/)" field.**

![](https://image.scribehow-prod.com/Ik2Wj8jstUnLiiGMIWIvJ-5qKBSyT_WICh7zmSDABQI/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:1034:0/wm:0.8:nowe:255:-11:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3L2QzODEyZDY3LTZmNGItNDVkMy1iMWQ1LTU5ZDVlYTAyOThjYS9hc2NyZWVuc2hvdC5qcGVn)

**3. Type "aks"**

**4. Click "Kubernetes services"**

![](https://image.scribehow-prod.com/GjJNvyZdJMk2Vs_IZVGMeKLHG5AlY1EFpFGcKXf9pvY/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:1468:0/wm:0.8:nowe:255:105:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3Lzc5NjIzMjNmLWQ4NGQtNDk4YS05NTJmLTczMWI5NzllMTVjNC9hc2NyZWVuc2hvdC5qcGVn)

**5. Click this icon to begin creating a Kubernetes service deployment.**

![](https://image.scribehow-prod.com/uuRSFQGpBDUuCNLe39ZZDsIj0xOXdC8DIzXz06vbe7M/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:1360:380/wm:0.8:nowe:255:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3LzI4N2U3N2QzLWFiOTktNDU0MC05MmJiLWI2OGY5ZjliZTU0ZS9hc2NyZWVuc2hvdC5qcGVn)

**6. Click "Create a Kubernetes cluster" to begin the workflow.**

![](https://image.scribehow-prod.com/hMCNhE310SNiorJ_I4euUp1WQlXCXGi74nCQAgg79_4/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:1366:415/wm:0.8:nowe:255:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3L2FmYzk5YTRmLTAxNWUtNGI2MS1hMWI1LWYzN2M4OGFmNmFmYi9hc2NyZWVuc2hvdC5qcGVn)

**7. Click "(New) Resource group" for the AKS deployment; both AWS and Azure have the concept of Resource Groups; some key items are that one Azure resource is always associated with one resource group and it can be organized via tags. You can also manage them with the Web Interface (Azure Portal), REST API, Command Line, PowerShell, or ARM Templates.**

![](https://image.scribehow-prod.com/55oKPkTYikFPpFd8aymL0oAr1rNkc0M6V_Pym9TExSs/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:14:206/wm:0.8:nowe:255:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3LzQ2NzRhNmQxLWI0M2MtNGQ5MC1iM2ViLWIzNGZmYmVjNjI5YS9hc2NyZWVuc2hvdC5qcGVn)

**8. I have an example Resource Group created named "rk-aks-demo" that I will use.**

![](https://image.scribehow-prod.com/D585R2sQnrSabaIRIECk04_OvyQXUvjjkjKFYlfda5A/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:88:372/wm:0.8:nowe:255:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3Lzg5MmQwOGY5LWQ5MzAtNDE1MS1iZDQ5LTIyYzQzZjhiMTIyZC9hc2NyZWVuc2hvdC5qcGVn)

**9. For demo purposes, we will use the "Dev/Test" Cluster preset configuration. One advantage in this workflow compared to AWS is that we offer several presets. These are 5 levels of presets that offer different advantages for cost and features/workloads that can get you started quick.**

![](https://image.scribehow-prod.com/biD235JbQ1edFt6sezd1JGMZgk4rdnMkst_5cw2yRgA/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:103:296/wm:0.8:nowe:255:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3L2ExNThhYTMwLTAyN2UtNDg5Zi1hMzE3LWZlOWU3MDhiYWQ0My9hc2NyZWVuc2hvdC5qcGVn)

**10. For demo purposes and Dev/Test environment, click "Best for experimenting with AKS or deploying a test app." Dev/Test will set system node pool size to B4ms shape with Cluster Autoscaling and 99.5% API server availability.**

![](https://image.scribehow-prod.com/1SVubvjGwnuj7aHyeYPQ5o7Hoh_bk5yK0FAOIfcMC4g/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:143:428/wm:0.8:nowe:255:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3L2M2MDcxYzI3LWY4ZjYtNDU5Yi05ZmVjLWYzMmIxOGY5YWYzYS9hc2NyZWVuc2hvdC5qcGVn)

**11. Create a name for your cluster - click the "Kubernetes cluster name" field and enter it.**

![](https://image.scribehow-prod.com/4nAzOegl6eNNxev_W2876QdXHAWVdk9s2boWXt-fcCM/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:98:398/wm:0.8:nowe:255:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3L2MyNTkwMjQzLTc3NzAtNDQ5Yy04YjA4LTY0N2NmZDU2YmJlMC9hc2NyZWVuc2hvdC5qcGVn)

**12. Since I live close to Central US Azure datacenter, I chose it as my Region. Click "(US) Central US"**

![](https://image.scribehow-prod.com/8wUGizLUswpFrj-0qbH2UGdNWwFsQzxj3kIGF3VbahM/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:87:434/wm:0.8:nowe:255:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3L2Q4MTA4OTVkLWM3YWEtNDRjNy1iYmYyLTZlMGE0YTgzODVmMC9hc2NyZWVuc2hvdC5qcGVn)

**13. During setup of AKS, it is important to understand production workloads and plan for resilience against datacenter failures. AKS clusters that are deployed using availability zones can distribute nodes across multiple zones within a single region - improving cluster availability. This is also the recommended approach when considering migrating from Amazon EKS to AKS.**

![](https://image.scribehow-prod.com/2-E1ufhAIztx17VkoLP-2Xmc-j8YvI9WnhaQoc_d1bE/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:66:479/wm:0.8:nowe:255:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3L2U3NDQ3MTRhLTdjYjItNDk1ZC05MGViLTBiMDc5ZGRhNTFkMi9hc2NyZWVuc2hvdC5qcGVn)

**14. Description of Availability Zones during setup.**

![](https://image.scribehow-prod.com/NPn5p_xwajfmQwKy-V_ChmDgKEgyITJtfJ71z41tMoU/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:0:479/wm:0.8:nowe:79:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3LzUzYTQzNTBiLTVjY2QtNDkzNy04OGJlLWQ5MzE5MWEzNDcwOS9hc2NyZWVuc2hvdC5qcGVn)

**15. We will use the default k8s version selected. Click "1.23.12 (default)" - you have the option to move to older and new (preview) releases right from the start. When migrating from EKS to AKS it is important to ensure your target k8s version is within the supported window for AKS.**

![](https://image.scribehow-prod.com/87R2wGOai6clvuQ-43_KsgtGvEg820SyBeOWD1F9H98/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:0:516/wm:0.8:nowe:253:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3LzgxNjUxZGEwLWI1OGYtNGE0MS05YTI3LTQwOWVlMWI3ZmNkNS9hc2NyZWVuc2hvdC5qcGVn)

**16. Since this is a demo, we can select 99.5% API server availability.  API server availability is an uptime service level agreement that guarantees a Kubernetes API server uptime of 99.95% clusters with one or more availability zones and 99.9% for all other clusters. **

![](https://image.scribehow-prod.com/-WoFDJtXQRTt8vwagWSvUOvwovbAvHzveNuWxYfx3qk/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:0:557/wm:0.8:nowe:99:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3LzU1OWRjODQyLTRlNzMtNDViYy1iZWFlLWQyZmQ4MzAxNGY1MC9hc2NyZWVuc2hvdC5qcGVn)

**17. In continuation of selecting an appropriate k8s version in line with our considerations from EKS to AKS, we can also select automatic upgrades. "Enabled with path (recommended)" will update the cluster to the latest patch version within the set minor version. We also have the option to select stable, rapid, node image, and disabled - depending on our workloads on EKS we might select stable for production workloads.**

![](https://image.scribehow-prod.com/bC1-aVnBDhegly6vVWBU6Eg_UZvFJH8uvalZ2hz7Jks/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:99:690/wm:0.8:nowe:255:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3L2IyMWM5NzY1LWRkMzUtNDIyMC05MDBjLThiNmFiNGRjYzVkMy9hc2NyZWVuc2hvdC5qcGVn)

**18. Sizing the k8s nodes is important when considering EKS to AKS. The types of workloads and their usage will influence the choice of how many nodes and what node size we use for the cluster. It is also important to consider valid quotas for the migration - you should verify that your quotas and limits are sufficient for these resources and if necessary, request and increase in vCPU quota.**

![](https://image.scribehow-prod.com/skhRxFw-ms55xq1rBi3_14fA0RDMAnmZ_YnHGy780hE/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:0:768/wm:0.8:nowe:57:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3L2YxODRkOWI3LTFlYTctNDIyYy1iNzg3LTQ5ZjFmZmMzNzc3My9hc2NyZWVuc2hvdC5qcGVn)

**19. We can also select the min and max of nodes to use for autoscaling. If your EKS cluster uses autoscaling and was engineered for high availability and business continuity with respect to elasticity - then the number of nodes is important.**

![](https://image.scribehow-prod.com/kv5xoaIJ1aWyC0COEMDgCEDcPdm1i3Ru18_siLbj0-M/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:0:869/wm:0.8:nowe:213:193:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3L2FiMzZiMjliLTFhNGQtNDRhYy1iOTQ5LWU2NTNhYTA0MWYyNi9hc2NyZWVuc2hvdC5qcGVn)

**20. Go to the next page and click "Next: Node pools >" Here we can configure additional node pools to handle a variety of workloads and in contrast to some of the obscurity in EKS, we can enable "virtual nodes" right from the start for Azure Container Instance fast burst scaling. We can also select the type of node pool OS disk encryption - important if you are planning to migrate from EKS with your own keys.**

![](https://image.scribehow-prod.com/1tew8y235yb--8tp6t9lhuHDHNTV3lzJSJNd-n1NMVo/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:37:869/wm:0.8:nowe:255:259:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3LzNkY2Q2NjdmLTRkOGYtNDhhMC1hYjVhLWQ1YWQ2N2Y2OGU3My9hc2NyZWVuc2hvdC5qcGVn)

**21. Next, we can move to Access. Click "Next : Access >"**

![](https://image.scribehow-prod.com/yQWdrGsCBtLNmdnWg1DNMSM7E-DHXd9Vcvbsn08v1r4/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:44:869/wm:0.8:nowe:255:261:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3LzAxNzQ4NWEyLTY4ZDQtNDc5My04MjM4LWZmN2IxOWFkMjE5OC9hc2NyZWVuc2hvdC5qcGVn)

**22. AKS setup allows for 3 types of authentication and authorization: Local accounts with k8s RBAC, Azure AD authentication with k8s RBAC, and Azure AD authentication with Azure RBAC. One strength of AKS is its tight coupling with Azure AD to use Azure role assignments for authorization checks on the cluster.**

![](https://image.scribehow-prod.com/70mg5U0jlFBBKI3DyHBgSfgxe8vPXTPpflzfqocSWS4/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:24:131/wm:0.8:nowe:255:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3LzEwOWE0NGFjLTRlMDctNGMxYi1iZTQ3LTYyNGQzMWY5NTA1YS9hc2NyZWVuc2hvdC5qcGVn)

**23. Next, we will go to the Networking overview. Click "Next : Networking >"**

![](https://image.scribehow-prod.com/LrTQffxkbf9AR5Opm2-WA9U8napi-p2ri8SXN3W7EmA/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:57:869/wm:0.8:nowe:255:258:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3L2UyMmZjNGQ5LTdlMTItNDU3Ny05OTcwLTU0NzgzYjFiZDI4Yy9hc2NyZWVuc2hvdC5qcGVn)

**24. Networking is very important when considering migrating from EKS to AKS. It is important to inventory the range of services and applications that uses them in the EKS cluster and then follow best practices for downtime handling. You might typically migrate over time rather than all at once, meaning old and new enviroments might need to communicate over the network. If an application previously used ClusterIP services to communicate might need to be exposed as LoadBalancer type and secured appropriately after the migration. Ideally, you want to point clients to new services that are running on AKS and we recommend that you redirect traffic by updating DNS to point to the Load Balancing sitting in front of your AKS cluster - Azure Traffic Manager can direct customers to the desired k8s cluster and application instance.**

![](https://image.scribehow-prod.com/5G1EC6yCvsxcLzR4kkg1yx1m9fnxBkULqDRdqwVgtZM/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:0:174/wm:0.8:nowe:193:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3L2FhYTBkNWU3LWRiY2EtNDUwNy1iYThkLWMwMjlhMTkwNTkyZC9hc2NyZWVuc2hvdC5qcGVn)

**25. In the network section, we can define and create a new virtual network. Both Azure VNet and AWS VPC segregate networks with subnets. Azure VNet assigns resources connected and deployed to the VNet a private IP address for the CIDR block specified and the smallest subnet supported is /29 and largest is a /8. Record the CIDR block range you need when migrating from EKS to AKS for k8s services and and the cluster as you do not want to experience IP exhaustion and also want to be able to scale accordingly.**

![](https://image.scribehow-prod.com/26479bhDGn2EjWN2Vas76KcEGnL8bCf4vnB3trgRcm0/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:0:286/wm:0.8:nowe:81:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3LzkyZjUxOTdmLWFhMmUtNDRjMy1iYzRjLTEzMDI4NTFmMmNmOC9hc2NyZWVuc2hvdC5qcGVn)

**26. The k8s service address range description.**

![](https://image.scribehow-prod.com/wPhhTzP3hCm8vIHib5sVJmX83zi0O1f9aRCjm1yb4QM/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:0:382/wm:0.8:nowe:156:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3L2QwZThiMDNlLTgwYTgtNGVjNS1iZDVlLTEzNTdiM2I0ZjkyZC9hc2NyZWVuc2hvdC5qcGVn)

**27. The k8s DNS service IP address description.**

![](https://image.scribehow-prod.com/Qf9UdLnZdQghGGEU-Nf7L9HVpgBhmoMISr0Thhz-yp0/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:0:412/wm:0.8:nowe:165:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3LzBjNWFmNmU5LTI2ZjAtNDhjOC04OWU4LWUwZTY4ODJjODJiNi9hc2NyZWVuc2hvdC5qcGVn)

**28. You can also change the network for the Docker Bridge address - Click "Docker Bridge address"**

![](https://image.scribehow-prod.com/SHgzwJDnovtB7-rbgFXYWiBZEeQtZtxahw8hNHuXfsw/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:0:463/wm:0.8:nowe:106:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3Lzc2Nzg1Y2QzLWE4MzEtNDQ5Ni1iNDdhLTgwZWE0NThhMjRiNC9hc2NyZWVuc2hvdC5qcGVn)

**29. Description for DNS name prefix for the hosted k8s API server FQDN - important to consider when migrating as this will be used to connect to when managing containers after creating the cluster.**

![](https://image.scribehow-prod.com/Y6CRlrAaOQMM_HgtwYTdPyQXj8PvXg2xOmOvuvpK9S8/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:0:501/wm:0.8:nowe:87:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3LzQxMjNhMjg4LTI2NjMtNGJjOC1hNTZhLTRjMTNmY2Y4NmRjOC9hc2NyZWVuc2hvdC5qcGVn)

**30. Enabling "HTTP Application Routing" will configure an ingress controller in your AKS cluster and as applications are deployed, the ingress controller will create publicly accessible DNS names for your application endpoints. Consider what this might mean for your applications as your migrate over - how many and what needs to be publicly available via ingress and what type of configurations are currently in place that need to be done in the new cluster.**

![](https://image.scribehow-prod.com/BlgdeW1vGHbwwZrM07G3M2RdMkxtlr82Yl1ckcgk3aM/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:0:773/wm:0.8:nowe:71:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3L2VkZmUzZDQwLTU2YTQtNDgxZi05MDE1LWFlZTNkZTFkZTNkNi9hc2NyZWVuc2hvdC5qcGVn)

**31. In this section, we can select the type of network policy structure for the k8s cluster. We can use Calico or Azure - Azure being one of the key differentiators out of the box vs EKS. Azure allows for Azure Network Policies via Azure Network Policy Manager (NPM) which uses IPTables for Linux and Host Network Service (HNS) ACLPolicies for Windows.**

![](https://image.scribehow-prod.com/vUVRqqu6L7MDOBzwBzpGljpWgj7ww4vuXTiZ12BygkI/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:45:869/wm:0.8:nowe:255:204:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3LzBiYTAwM2NjLWQ5ZDAtNDgyOS1hMjdkLTI4N2FkZGU0M2I2Ni9hc2NyZWVuc2hvdC5qcGVn)

**32. Click "Next : Integrations >"**

![](https://image.scribehow-prod.com/EHFTSNfSZjWKrqz78xFfiL9rzZeLWu3etbOFha6nYjw/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:42:869/wm:0.8:nowe:255:262:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3LzA4MTZlNTc0LWI5OTYtNDViZC1hNDdmLTU5ZThkMDcwZTc1ZS9hc2NyZWVuc2hvdC5qcGVn)

**33. Out of the box, we can enable Microsoft Defender for Cloud which provides unified security management and threat protection across the workloads - importantly when migrating production workloads we want to consider the security policies and protection against threats as we build in AKS. Using Defender backed with Azure Monitor and Azure Policy allows for threat protection, container insights, and at-scale enforcements and safeguards for AKS clusters in a centralized, consistent manner through Azure Policy.**

![](https://image.scribehow-prod.com/vDQVPX2x1V8O5TgU1-mNHoZq0yurqwBrg2wnDXY_JgE/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:0:251/wm:0.8:nowe:237:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3Lzc3NjA3MjYwLTU0ODktNGJmNy04MzJiLTZmZjZkMTY2YTYwOC9hc2NyZWVuc2hvdC5qcGVn)

**34. When migrating from EKS to AKS, we likely will have a set of images that are pre-built or need built for the new cluster; we can use tools like Azure Migrate to help with that along with connecting the AKS cluster to Azure Container Registry to store and use these images.**

![](https://image.scribehow-prod.com/t22ouZ4i8dC59EuCLP9w7UMhBQEsdqCVljtcBALbTTo/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:0:273/wm:0.8:nowe:223:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3LzdiOGI5N2ZhLWZiOGYtNDE1YS04YTc0LWNhYzgyZWI1YWJkMi9hc2NyZWVuc2hvdC5qcGVn)

**35. Click "Next : Advanced >"**

![](https://image.scribehow-prod.com/v_d1xGgUfp7MvFYq0x6RKDljz2jhhSkV-pO4SYBnhnU/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:42:869/wm:0.8:nowe:255:261:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3L2VkNDgzOWE5LTUwMDItNGI0MC04NzU5LWEyZmE5ZDgyODhlYy9hc2NyZWVuc2hvdC5qcGVn)

**36. When migrating from EKS to AKS, it is important to know the type of data persistence and where the new data will be stored. When we create AKS cluster we have the option to enable secret store CSI driver which also allows us to integrate Azure Key Vault secrets. Ideally, when we migrate persistent volumes, we want to quiesce writes to the application, take snapshosts of the disks, create new managed disks from the snapshots, create persistent volumes in AKS, update the pod spec to use existing volumes rather than static provisioning, then deploy the application to AKS, validate it and point live traffic to the new cluster. You can use tools like Azure CLI Disk Copy extension and Azure Kube CLI extension to migrate volumes between k8s clusters.**

![](https://image.scribehow-prod.com/n4gqIe0FeAgz_p6rTXhYwbjkmyc0l17-oHj1jhv28nA/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:0:0/wm:0.8:nowe:187:128:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3LzU2Nzg2OGNiLTAwOTgtNDY2My1hM2ZmLTNmNDY1NWE3YTNmOC9hc2NyZWVuc2hvdC5qcGVn)

**37. Click "Next : Tags >" here we can tag the AKS cluster for certain things like environment.**

![](https://image.scribehow-prod.com/FDIivbMXzFt9C-BJxNk1UmmbaiaP0d23XqiLYQAOYcg/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:16:869/wm:0.8:nowe:255:262:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3L2RkYzZiZDk0LTI5MjgtNGU5NC04NDI1LWI5YzRjNmM5ZWFhYy9hc2NyZWVuc2hvdC5qcGVn)

**38. We're ready to create our AKS cluster! Click "Next : Review + create >"**

![](https://image.scribehow-prod.com/F0jtKYhro1vP282FATJ7RalsRPfvHYVFUI5MzL3ozBQ/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:63:869/wm:0.8:nowe:255:259:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3LzBlM2I2MDQxLTAxMmQtNDI5NC1hNjVkLTVmOTI2YjJlYzY4Yy9hc2NyZWVuc2hvdC5qcGVn)

**39. After the cluster has been provisioned, we can connect to it by clicking "Connect to cluster"**

![](https://image.scribehow-prod.com/oKtK5-7JbG0n3NUbApLGeVp1pHVGto2YiO7rJiKTAXQ/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:161:292/wm:0.8:nowe:255:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3L2RlMGUxZDE4LWExNDItNDY0Yi05NjM4LTdiMWYwYjM0N2ZjZS9hc2NyZWVuc2hvdC5qcGVn)

**40. We can quickly get a snapshot of the current environment using Cloud Shell - Click "Open Cloud Shell" - from here it gives us all the commands to run and even sets the accout and credentials for us when we open Cloud Shell - then from here we can get deployments and list namespaces and being our EKS to AKS migration!**

![](https://image.scribehow-prod.com/r7qNBUAwIW80iwNggqimSz2pnxQaDVzGTj1PZKTKadI/zoom:0.7506702412868632/enlarge:true/crop:746:420:nowe:0:2/wm:0.8:nowe:49:132:0.17857142857142858/aHR0cHM6Ly9jb2xvbnktcmVjb3JkZXIuczMuYW1hem9uYXdzLmNvbS9maWxlcy8yMDIyLTEyLTA3Lzg4MWFjNDZmLThkYmItNDZjMi1hODNkLTM5YTViZWRmMWUxNC9hc2NyZWVuc2hvdC5qcGVn)
#### [Made with Scribe](https://scribehow.com/shared/Step-by-Step_AKS_Workflow_-_EKS_to_AKS_Considerations__O2mSEOO4Q0mPy_VWTijcBw)


