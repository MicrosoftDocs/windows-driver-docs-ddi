---
UID: NF:ndis.NdisFillMemory
title: NdisFillMemory macro
author: windows-driver-content
description: The NdisFillMemory function fills a caller-supplied buffer with the given character.
old-location: netvista\ndisfillmemory.htm
old-project: netvista
ms.assetid: 6d974c56-5925-4ad5-a3c0-0c17e8488431
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisFillMemory, NdisFillMemory macro [Network Drivers Starting with Windows Vista], ndis/NdisFillMemory, ndis_memory_ref_c1411624-0e7b-40e2-9812-4426b2a9f2bc.xml, netvista.ndisfillmemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlFillMemory instead.
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
req.lib: 
req.dll: 
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisFillMemory
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFillMemory macro


## -description


The 
  <b>NdisFillMemory</b> function fills a caller-supplied buffer with the given character.


## -syntax


````
VOID NdisFillMemory(
  [in] PVOID Destination,
  [in] ULONG Length,
  [in] UCHAR Fill
);
````


## -parameters




### -param Destination [in]

A pointer to the buffer to be filled.


### -param Length [in]

The number of bytes to be filled.


### -param Fill [in]

The value to fill the buffer.


## -remarks



Callers of 
    <b>NdisFillMemory</b> can be running at any IRQL, provided that the 
    <i>Destination</i> buffer is resident. If the buffer is pageable, a caller must be running at IRQL &lt;
    DISPATCH_LEVEL.




## -see-also

<a href="..\wdm\nf-wdm-rtlequalmemory.md">RtlEqualMemory</a>



<a href="..\wdm\nf-wdm-rtlzeromemory.md">RtlZeroMemory</a>



 

 


