---
UID: NF:bdasup.BdaPropertyNodeProperties
title: BdaPropertyNodeProperties function (bdasup.h)
description: The BdaPropertyNodeProperties function retrieves a list of properties that a node supports.
old-location: stream\bdapropertynodeproperties.htm
tech.root: stream
ms.assetid: 1f50bf08-6134-4a97-8c9c-adc9ad697154
ms.date: 04/23/2018
ms.keywords: BdaPropertyNodeProperties, BdaPropertyNodeProperties function [Streaming Media Devices], bdaref_fc328c79-7b0b-4646-91cd-3e4957b30b2a.xml, bdasup/BdaPropertyNodeProperties, stream.bdapropertynodeproperties
ms.topic: function
f1_keywords:
 - "bdasup/BdaPropertyNodeProperties"
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
- BdaPropertyNodeProperties
product:
- Windows
targetos: Windows
req.typenames: 
---

# BdaPropertyNodeProperties function


## -description


The <b>BdaPropertyNodeProperties</b> function retrieves a list of properties that a node supports. 


## -parameters




### -param pIrp




### -param pKSProperty [in]

Points to a <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property and request type of the property request.


### -param pguidProperty [out, optional]

Points to an array that receives the list of GUIDs for the properties supported by a node.


#### - Irp [in]

Points to the IRP for the request to retrieve the list of properties for a node. The BDA minidriver receives this IRP with the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-bda-node-properties">KSPROPERTY_BDA_NODE_PROPERTIES</a> request.


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <b>BdaPropertyNodeProperties</b> function to retrieve the list of properties for a node after the minidriver receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-bda-node-properties">KSPROPERTY_BDA_NODE_PROPERTIES</a> request of the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-bdatopology">KSPROPSETID_BdaTopology</a> property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaPropertyNodeProperties</b> function directly, without intercepting this request using an internal get-handler (<a href="https://docs.microsoft.com/previous-versions/ff567177(v=vs.85)">KStrGetPropertyHandler</a>). See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/defining-automation-tables">Defining Automation Tables</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/determining-bda-device-topology">Determining BDA Device Topology</a> for more information. 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-bda-node-properties">KSPROPERTY_BDA_NODE_PROPERTIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-bdatopology">KSPROPSETID_BdaTopology</a>
 

 

