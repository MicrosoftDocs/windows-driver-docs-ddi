---
UID: NF:ndis.NdisGetSharedDataAlignment
title: NdisGetSharedDataAlignment function
author: windows-driver-content
description: NdisGetSharedDataAlignment returns the preferred alignment for memory structures that can be shared by more than one processor.
old-location: netvista\ndisgetshareddataalignment.htm
old-project: netvista
ms.assetid: 561315b4-8866-4f48-8138-12b1a38f743e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisGetSharedDataAlignment, NdisGetSharedDataAlignment function [Network Drivers Starting with Windows Vista], miniport_memory_shared_ref_1572f536-6b6a-4ea9-9150-78399870538c.xml, ndis/NdisGetSharedDataAlignment, netvista.ndisgetshareddataalignment
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisGetSharedDataAlignment   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisGetSharedDataAlignment   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisGetSharedDataAlignment
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisGetSharedDataAlignment function


## -description


<b>NdisGetSharedDataAlignment</b> returns the preferred alignment for memory structures that can be shared
  by more than one processor.


## -syntax


````
ULONG NdisGetSharedDataAlignment(void);
````


## -parameters






## -returns



The boundary value, in bytes, on which drivers should align structures that can be shared by more
     than one processor.




## -remarks



Use 
    <b>NdisGetSharedDataAlignment</b> to determine the best alignment for data structures that will be shared
    between processors. Using the returned value when allocating such structures minimizes cache effects that
    reduce the performance of multiprocessor systems.

System support for 
    <b>NdisGetSharedDataAlignment</b> is available in Windows XP and later versions.



