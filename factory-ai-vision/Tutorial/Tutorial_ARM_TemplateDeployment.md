
# ARM Template Deployment :


## Prerequisites

To install ARM Template Deployment, the following prerequisites are required:

1.	You must have an Azure subscription. 
if you don’t have one, you can create one here: https://azure.microsoft.com/en-us/pricing/purchase-options/pay-as-you-go/

2.	That subscription must contain Azure Stack Edge or IoT hub Edge device with port 8181 opened. please follow this documentation for deployment information 

3.	Azure Custom Vision account, see the below link to find your training key here and learn more here
<br/><br/>

![Diagram - Custom vision setting path](
https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot1.png) 
<br/><br/>


## Step 2: Click on the setting icon on the top

## Step 3: Create a new account, can get the app at the Azure Marketplace

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot1.1.png) 
<br/><br/>

## Please follow below links for reference


•	https://docs.microsoft.com/en-us/azure/cognitive-services/custom-vision-service/getting-started-build-a-classifier#create-custom-vision-resources

•	https://portal.azure.com/?microsoft_azure_marketplace_ItemHideKey=microsoft_azure_cognitiveservices_customvision#create/Microsoft.CognitiveServicesCustomVision

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot1.2.png) 
<br/><br/>


![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot1.3.png) 
<br/><br/>


## Step4: Choose the resources under the account; you will see information of “Key” and “Endpoint”

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot2.png) 
<br/><br/>

## Additonal Prerequisites
## 1.	Create an IoT Hub using the Azure portal 
Please find the information by below URL 
https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-create-through-portal 
## 2.	Install Azure IoT Edge for Linux  
Please find the information by below URL 
https://docs.microsoft.com/en-us/azure/iot-edge/how-to-install-iot-edge?view=iotedge-2020-11

# Get Started :

## 	Step 1: Open your browser and paste the link

https://portal.azure.com/#create/Microsoft.Template

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot3.png) 
<br/><br/>

## Step 1.1: Please fill the below mandatory field and check the below instruction of each field to decide the information needed for go ahead.

### 1.1.1 : Subscription:

Definition:  All resources in an Azure subscription are billed together.  
 Example: Microsoft Azure Sponsorship

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot4.png) 
<br/><br/>

### 1.1.2: Resource Group: 

Definition:  A resource group is a collection of resources that share the same life cycles, permissions and policies.  
Example: customvision

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot5.png) 
<br/><br/>

A resource group can be created by click “Create new”

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot6.png) 
<br/><br/>

## Step 1.2: Please fill “Instance Details” as below:

### 1.2.1: Region:

Definition:   Choose the Azure region that’s right for you and your customers. Not every resource is available in every region.  
Example: East US

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot7.png) 
<br/><br/>

### 1.2.2: Device Architecture: 
Definition:   Specify the Architecture of the Edge Device. Currently supported values are “X86” and “ARM64”. 
Example: X86 or ARM64

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot8.png) 
<br/><br/>

### 1.2.3: Module Runtime: 
Definition:   Select value for Runtime for detector module on Edge Device.  
•	Set it to “CPU” to use if CPU to run detector module. 
•	If the Edge device has Nvidia GPU  
o	set it to NVIDIA to use GPU to run detector module  
o	or to use movidius set it to “MOVIDIUS“

Example:  
o	If You selected X86 in Device Architecture in 1.2.2 then you will see below option 
   •	cpu 
   •  gpu (NVIDIA cude 11) 
   •	vpu(Movidius) 
o	If You selected ARM64 in Device Architecture in 1.2.2 then you will see below option 
   • Jetson(Jetpack 4.4)

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot9.png) 
<br/><br/>


### 1.2.4: Video Capture Module: 
Definition:   Select video capture module to deal with the media source.  
•	Live Video Analytics (LVA): is a series from Microsoft that enables developers to capture, record, analyze live video and publish the results (video  and /or video analytics) to Azure services (in the cloud and/or the edge) 
•	OpenCV: is an open source library that includes several hundreds of computer vision Algorithm.

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot10.png) 
<br/><br/>

### 1.2.5: IOT HUB Name: 
Definition:   Enter the Name of Existing IOT Hub learn more from link

https://portal.azure.com/#@linkernetworks.com/resource/subscriptions/091725d9-aeba-4638-8faf-d0e81a03a93d/resourceGroups/customvision/providers/Microsoft.Devices/IotHubs/customvision/Overview

Example: customvision

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot11.png) 
<br/><br/>


### 1.2.6: Edge Device Name: 
Definition:   Enter the existing IOT Hub Edge Device. learn more from link

https://portal.azure.com/#@linkernetworks.com/resource/subscriptions/091725d9-aeba-4638-8faf-d0e81a03a93d/resourceGroups/customvision/providers/Microsoft.Devices/IotHubs/customvision/EdgeExplorer

Example: cam5

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot12.png) 
<br/><br/>


### 1.2.7: Custom Vision Name: 
Definition:   Enter the existing CustomVision service. learn more from link 

https://www.customvision.ai/projects
Example: factoryai

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot13.png) 
<br/><br/>

### 1.2.8: Media Service Name: (Optional) 
Definition: Enter the name of existing Azure Media Service. 
NOTE: ONLY REQUIRED WHEN choose Media service as LVA in 1.2.4  
Example:

•	Go to Azure portal https://portal.azure.com 
•	and search media Services to choose the media service name

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot14.png) 
<br/><br/>

### 1.2.9: Media Service Resource Group: 
Definition: Enter the resource group of existing Azure Media Service. 
NOTE: ONLY REQUIRED WHEN choose Media service as LVA in 1.2.4  
Example:
•	Go to Azure portal https://portal.azure.com 
•	and search media Services to choose the media service name 
•	check the Resource group name

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot15.png) 
<br/><br/>


### 1.2.10: Media Service Principal Name: 
Definition: Enter the name of existing Azure Media Principal Name. 
NOTE: ONLY REQUIRED WHEN choose Media service as LVA in 1.2.4  
Please follow below links for more information

•	https://docs.microsoft.com/en-us/azure/media-services/live-video-analytics-edge/get-started-detect-motion-emit-events-quickstart

•	https://docs.microsoft.com/en-us/azure/media-services/live-video-analytics-edge/detect-motion-record-video-clips-media-services-quickstart

Example:   
•	Go to Azure portal https://portal.azure.com 
•	and search media Services to choose the media service name 
•	click on API Access Tab  
•	Create New of Select running AAD application  
•	Choose “select”




### 1.2.11: Media Service Principal Secret: (Optional) 
Definition: Enter the name of existing Azure Media Principal Secret. 
NOTE: ONLY REQUIRED WHEN choose Media service as LVA in 1.2.4

Example:   
•	Go to Azure portal https://portal.azure.com 
•	and search media Services to choose the media service name 
•	click on API Access Tab
•	Create New of secret of selected AAD application  
•	click “select” after choose Expires  
o	in one year 
o	in 2 years 
o	Never 
•	Copy AAD Client ID  
•	Copy AAD Client Secret

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot16.png) 
<br/><br/>

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot17.png) 
<br/><br/>

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot18.png) 
<br/><br/>

### •	Copy AAD client ID and Copy AAD Client Secret in ARM Template Custom Deployment form’s below field

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot19.png) 
<br/><br/>

## 1.3: After Filled above fields as definition we will have below two filled scenario 
### 1.3.1: When Video Capture Module = LVA

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot20.png) 
<br/><br/>

### •	Then click “Review + Create”

### 1.3.2: When Video Capture Module = OpenCV

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot21.png) 
<br/><br/>

### •	Then click “Review + Create”  
1.4: After click “Review + Create” in step 1.3 Deployment Process will as below screen

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot22.png) 
<br/><br/>

•	Press “Create” for finish the deployment.  
Note: The Installation will take some time. Please wait for couple of minutes to complete the installation. 
You can check the deployment on the Azure portal.

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot23.png) 
<br/><br/>

### •	Press “Go to Resource Group” to get selected “Edge Device Name” to get the IP address. 
For example: Edge Device Name = cam5

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot24.png) 
<br/><br/>


### •	Press Edge device Name “cam 5” to get selected get the IP address.

![Diagram - Custom vision Market place path](https://github.com/linkernetworks/azure-intelligent-edge-patterns/raw/linker/factory-ai-vision/assets/Tutorial_ArmTemplate_Deployment_Screenshot25.png) 
<br/><br/>


## 1.5: Open Your Browser, Connect to Public IP Address: Port 8181 
       Example:  https://168.63.246.174:8181
