---
UID: NF:bdasup.BdaPropertyGetControllingPinId
title: BdaPropertyGetControllingPinId function
author: windows-driver-content
description: The BdaPropertyGetControllingPinId function retrieves the identifier of a pin on which to control the properties, methods, and events of a specific node.
old-location: stream\bdapropertygetcontrollingpinid.htm
tech.root: stream
ms.assetid: 3d4d4124-9c52-42f5-bc31-b924d9c15c36
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: BdaPropertyGetControllingPinId, BdaPropertyGetControllingPinId function [Streaming Media Devices], bdaref_7f3a3695-4599-4b16-8a90-4ac171ab1ec0.xml, bdasup/BdaPropertyGetControllingPinId, stream.bdapropertygetcontrollingpinid
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Bdasup.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Bdasup.lib
-	Bdasup.dll
api_name:
-	BdaPropertyGetControllingPinId
product:
- Windows
targetos: Windows
req.typenames: 
---

# BdaPropertyGetControllingPinId function


## -description


The <b>BdaPropertyGetControllingPinId</b> function retrieves the identifier of a pin on which to control the properties, methods, and events of a specific node. 


## -parameters




### -param Irp [in]

Points to the IRP for the request to retrieve the controlling pin for a node. The BDA minidriver receives this IRP with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564303">KSPROPERTY_BDA_CONTROLLING_PIN_ID</a> request.


### -param Property

TBD


### -param pulControllingPinId [out, optional]

Points to a variable that receives the identifier of the controlling pin for a node. 


#### - pProperty [in]

Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566716">KSP_BDA_NODE_PIN</a> structure that describes the property and request type of the property request to retrieve the controlling pin for a node. 


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <b>BdaPropertyGetControllingPinId</b> function to retrieve the identifier of the controlling pin for a node after the minidriver receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564303">KSPROPERTY_BDA_CONTROLLING_PIN_ID</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a> property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaPropertyGetControllingPinId</b> function directly, without intercepting this request using an internal get-handler (<a href="https://msdn.microsoft.com/library/windows/hardware/ff567177">KStrGetPropertyHandler</a>). See <a href="https://msdn.microsoft.com/1c0dace6-b618-4705-bf5d-65457d14c072">Defining Automation Tables</a> and <a href="https://msdn.microsoft.com/fdac317e-d4fc-47c9-87d3-bec597f758f5">Determining BDA Device Topology</a> for more information. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564303">KSPROPERTY_BDA_CONTROLLING_PIN_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566716">KSP_BDA_NODE_PIN</a>
 

 

