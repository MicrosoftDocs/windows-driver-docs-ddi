---
UID: NF:bdasup.BdaPropertyNodeDescriptors
title: BdaPropertyNodeDescriptors function
author: windows-driver-content
description: The BdaPropertyNodeDescriptors function retrieves a list of nodes in a template topology.
old-location: stream\bdapropertynodedescriptors.htm
tech.root: stream
ms.assetid: 46e38460-9284-4305-997d-bf72b308f301
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: BdaPropertyNodeDescriptors, BdaPropertyNodeDescriptors function [Streaming Media Devices], bdaref_67976a51-5f21-4369-be96-ab6a2b758e85.xml, bdasup/BdaPropertyNodeDescriptors, stream.bdapropertynodedescriptors
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
-	BdaPropertyNodeDescriptors
product:
- Windows
targetos: Windows
req.typenames: 
---

# BdaPropertyNodeDescriptors function


## -description


The <b>BdaPropertyNodeDescriptors</b> function retrieves a list of nodes in a template topology. 


## -parameters




### -param pIrp




### -param pKSProperty [in]

Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property and request type of the property request.


### -param pNodeDescriptorProperty






#### - Irp [in]

Points to the IRP for the request to retrieve the list of nodes. The BDA minidriver receives this IRP with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564324">KSPROPERTY_BDA_NODE_DESCRIPTORS</a> request.


#### - pguidProperty [out, optional]

Points to an array that receives the list of GUIDs for the nodes in a template topology. 


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <b>BdaPropertyNodeDescriptors</b> function to retrieve the list of nodes after the minidriver receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564324">KSPROPERTY_BDA_NODE_DESCRIPTORS</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a> property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaPropertyNodeDescriptors</b> function directly, without intercepting this request using an internal get-handler (<a href="https://msdn.microsoft.com/library/windows/hardware/ff567177">KStrGetPropertyHandler</a>). See <a href="https://msdn.microsoft.com/1c0dace6-b618-4705-bf5d-65457d14c072">Defining Automation Tables</a> and <a href="https://msdn.microsoft.com/fdac317e-d4fc-47c9-87d3-bec597f758f5">Determining BDA Device Topology</a> for more information. 

For a list of BDA nodes that are available to create in a template topology, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556529">BDA Node Category GUIDs</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564324">KSPROPERTY_BDA_NODE_DESCRIPTORS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a>
 

 

