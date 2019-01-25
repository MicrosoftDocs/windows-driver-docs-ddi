---
UID: NF:ks.KsCreateAllocator
title: KsCreateAllocator function (ks.h)
description: The KsCreateAllocator function creates a handle to an allocator for the given sink connection handle. This function does not complete the IRP or set the status in the IRP.
old-location: stream\kscreateallocator.htm
tech.root: stream
ms.assetid: c67e036c-9f4c-447e-94bb-73cf215c865a
ms.date: 04/23/2018
ms.keywords: KsCreateAllocator, KsCreateAllocator function [Streaming Media Devices], ks/KsCreateAllocator, ksfunc_cc89b86b-fdd7-4e08-83b1-0df712fccaa4.xml, stream.kscreateallocator
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ks.lib
-	ks.dll
api_name:
-	KsCreateAllocator
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsCreateAllocator function


## -description


The <b>KsCreateAllocator</b> function creates a handle to an allocator for the given sink connection handle. This function does not complete the IRP or set the status in the IRP.


## -parameters




### -param ConnectionHandle [in]

Specifies the handle to the sink connection on which to create the allocator.


### -param AllocatorFraming [in]

Specified framing for the allocator.


### -param AllocatorHandle [out]

Specifies the pointer to a handle to store the allocator handle.


## -returns



The <b>KsCreateAllocator</b> function returns STATUS_SUCCESS if successful, or it returns an error if unsuccessful. 




## -remarks



There are two versions of the <b>KsCreateAllocator</b> function: one for user-mode clients and one for kernel-mode clients. This function can only be called at PASSIVE_LEVEL for kernel-mode clients.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560979">KSALLOCATOR_FRAMING</a>
 

 

