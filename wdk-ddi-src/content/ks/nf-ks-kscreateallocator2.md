---
UID: NF:ks.KsCreateAllocator2
title: KsCreateAllocator2 function (ks.h)
description: Creates a handle to an allocator for the given sink connection handle. This function does not complete the IRP or set the status in the IRP.
old-location: stream\kscreateallocator2.htm
tech.root: stream
ms.assetid: f0efa17c-9318-46a4-bc08-d4d372cc07ba
ms.date: 04/23/2018
keywords: ["KsCreateAllocator2 function"]
ms.keywords: KsCreateAllocator2, KsCreateAllocator2 function [Streaming Media Devices], ks/KsCreateAllocator2, stream.kscreateallocator2
f1_keywords:
 - "ks/KsCreateAllocator2"
 - "KsCreateAllocator2"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ks.h
api_name:
- KsCreateAllocator2
targetos: Windows
req.typenames: 
---

# KsCreateAllocator2 function


## -description


Creates a handle to an allocator for the given sink connection handle. This function does not complete the IRP or set the status in the IRP.

Supported starting in Windows 8.


## -parameters




### -param ConnectionHandle [in]

Specifies the handle to the sink connection on which to create the allocator.


### -param AllocatorFraming [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing">KSALLOCATOR_FRAMING</a> structure that specifies framing for the allocator.


### -param AllocatorHandle [out]

Specifies the pointer to a handle to store the allocator handle.


## -returns



Returns <b>NOERROR</b> if successful; otherwise, returns an error code.




## -remarks



This is a new version of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kscreateallocator">KsCreateAllocator</a> function and uses the device broker to create the handle to the kernel streaming object. In addition, the Component Object Model (COM) <a href="https://docs.microsoft.com/windows/desktop/api/objbase/nf-objbase-coinitialize">CoInitialize</a> function must be called before this function is called.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/objbase/nf-objbase-coinitialize">CoInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing">KSALLOCATOR_FRAMING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kscreateallocator">KsCreateAllocator</a>
 

 

