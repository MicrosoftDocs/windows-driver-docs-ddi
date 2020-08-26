---
UID: NF:bdasup.BdaPropertyNodeDescriptors
title: BdaPropertyNodeDescriptors function (bdasup.h)
description: The BdaPropertyNodeDescriptors function retrieves a list of nodes in a template topology.
old-location: stream\bdapropertynodedescriptors.htm
tech.root: stream
ms.assetid: 46e38460-9284-4305-997d-bf72b308f301
ms.date: 04/23/2018
keywords: ["BdaPropertyNodeDescriptors function"]
ms.keywords: BdaPropertyNodeDescriptors, BdaPropertyNodeDescriptors function [Streaming Media Devices], bdaref_67976a51-5f21-4369-be96-ab6a2b758e85.xml, bdasup/BdaPropertyNodeDescriptors, stream.bdapropertynodedescriptors
f1_keywords:
 - "bdasup/BdaPropertyNodeDescriptors"
 - "BdaPropertyNodeDescriptors"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Bdasup.lib
- Bdasup.dll
api_name:
- BdaPropertyNodeDescriptors
targetos: Windows
req.typenames: 
---

# BdaPropertyNodeDescriptors function


## -description


The <b>BdaPropertyNodeDescriptors</b> function retrieves a list of nodes in a template topology. 


## -parameters




### -param pIrp




### -param pKSProperty 
[in]
Points to a <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property and request type of the property request.


### -param pNodeDescriptorProperty






#### - Irp [in]

Points to the IRP for the request to retrieve the list of nodes. The BDA minidriver receives this IRP with the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-bda-node-descriptors">KSPROPERTY_BDA_NODE_DESCRIPTORS</a> request.


#### - pguidProperty [out, optional]

Points to an array that receives the list of GUIDs for the nodes in a template topology. 


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <b>BdaPropertyNodeDescriptors</b> function to retrieve the list of nodes after the minidriver receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-bda-node-descriptors">KSPROPERTY_BDA_NODE_DESCRIPTORS</a> request of the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-bdatopology">KSPROPSETID_BdaTopology</a> property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaPropertyNodeDescriptors</b> function directly, without intercepting this request using an internal get-handler (<a href="https://docs.microsoft.com/previous-versions/ff567177(v=vs.85)">KStrGetPropertyHandler</a>). See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/defining-automation-tables">Defining Automation Tables</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/determining-bda-device-topology">Determining BDA Device Topology</a> for more information. 

For a list of BDA nodes that are available to create in a template topology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/bda-node-category-guids">BDA Node Category GUIDs</a>. 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-bda-node-descriptors">KSPROPERTY_BDA_NODE_DESCRIPTORS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-bdatopology">KSPROPSETID_BdaTopology</a>
 

 

