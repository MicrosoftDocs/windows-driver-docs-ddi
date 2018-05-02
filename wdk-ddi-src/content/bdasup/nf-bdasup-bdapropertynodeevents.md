---
UID: NF:bdasup.BdaPropertyNodeEvents
title: BdaPropertyNodeEvents function
author: windows-driver-content
description: The BdaPropertyNodeEvents function retrieves a list of events that a node supports.
old-location: stream\bdapropertynodeevents.htm
old-project: stream
ms.assetid: 8e646426-00c8-4a8c-8256-13a27ecea158
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: BdaPropertyNodeEvents, BdaPropertyNodeEvents function [Streaming Media Devices], bdaref_2c17ed4f-8a4c-41bc-b543-9b2e5b82834b.xml, bdasup/BdaPropertyNodeEvents, stream.bdapropertynodeevents
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
-	BdaPropertyNodeEvents
product:
- Windows
targetos: Windows
req.typenames: 
---

# BdaPropertyNodeEvents function


## -description


The <b>BdaPropertyNodeEvents</b> function retrieves a list of events that a node supports. 


## -parameters




### -param pIrp

TBD


### -param pKSProperty [in]

Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property and request type of the property request.


### -param pguidProperty [out, optional]

Points to an array that receives the list of GUIDs for the events supported by a node.


#### - Irp [in]

Points to the IRP for the request to retrieve the list of events for a node. The BDA minidriver receives this IRP with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564326">KSPROPERTY_BDA_NODE_EVENTS</a> request.


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <b>BdaPropertyNodeEvents</b> function to retrieve the list of events for a node after the minidriver receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564326">KSPROPERTY_BDA_NODE_EVENTS</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a> property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaPropertyNodeEvents</b> function directly, without intercepting this request using an internal get-handler (<a href="https://msdn.microsoft.com/library/windows/hardware/ff567177">KStrGetPropertyHandler</a>). See <a href="https://msdn.microsoft.com/1c0dace6-b618-4705-bf5d-65457d14c072">Defining Automation Tables</a> and <a href="https://msdn.microsoft.com/fdac317e-d4fc-47c9-87d3-bec597f758f5">Determining BDA Device Topology</a> for more information. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564326">KSPROPERTY_BDA_NODE_EVENTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a>
 

 

