---
UID: NF:bdasup.BdaPropertyNodeMethods
title: BdaPropertyNodeMethods function
author: windows-driver-content
description: The BdaPropertyNodeMethods function retrieves a list of methods that a node supports.
old-location: stream\bdapropertynodemethods.htm
tech.root: stream
ms.assetid: 52cb13a6-6efe-4934-a6ec-178d4b2afb0a
ms.date: 04/23/2018
ms.keywords: BdaPropertyNodeMethods, BdaPropertyNodeMethods function [Streaming Media Devices], bdaref_15a0d157-4e7d-43ae-9f1f-6ffb70bd4f9b.xml, bdasup/BdaPropertyNodeMethods, stream.bdapropertynodemethods
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
-	BdaPropertyNodeMethods
product:
- Windows
targetos: Windows
req.typenames: 
---

# BdaPropertyNodeMethods function


## -description


The <b>BdaPropertyNodeMethods</b> function retrieves a list of methods that a node supports. 


## -parameters




### -param pIrp




### -param pKSProperty [in]

Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property and request type of the property request.


### -param pguidProperty [out, optional]

Points to an array that receives the list of GUIDs for the methods supported by a node.


#### - Irp [in]

Points to the IRP for the request to retrieve the list of methods for a node. The BDA minidriver receives this IRP with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564328">KSPROPERTY_BDA_NODE_METHODS</a> request.


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <b>BdaPropertyNodeMethods</b> function to retrieve the list of methods for a node after the minidriver receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564328">KSPROPERTY_BDA_NODE_METHODS</a> request of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a> property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaPropertyNodeMethods</b> function directly, without intercepting this request using an internal get-handler (<a href="https://msdn.microsoft.com/library/windows/hardware/ff567177">KStrGetPropertyHandler</a>). See <a href="https://msdn.microsoft.com/1c0dace6-b618-4705-bf5d-65457d14c072">Defining Automation Tables</a> and <a href="https://msdn.microsoft.com/fdac317e-d4fc-47c9-87d3-bec597f758f5">Determining BDA Device Topology</a> for more information. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564328">KSPROPERTY_BDA_NODE_METHODS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566561">KSPROPSETID_BdaTopology</a>
 

 

