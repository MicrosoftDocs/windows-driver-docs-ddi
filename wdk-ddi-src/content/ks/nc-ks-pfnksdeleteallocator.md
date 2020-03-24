---
UID: NC:ks.PFNKSDELETEALLOCATOR
title: PFNKSDELETEALLOCATOR (ks.h)
description: An AVStream minidriver's AVStrMiniDeleteAllocator routine deletes the allocator that is associated with a pin.
old-location: stream\avstrminideleteallocator.htm
tech.root: stream
ms.assetid: 867da1f8-061b-4fc1-8e20-3ebc43300f15
ms.date: 04/23/2018
keywords: ["PFNKSDELETEALLOCATOR callback function"]
ms.keywords: AVStrMiniDeleteAllocator, AVStrMiniDeleteAllocator routine [Streaming Media Devices], PFNKSDELETEALLOCATOR, avstclbk_32e3c0fd-c437-45e0-8e5e-72f2f628ee51.xml, ks/AVStrMiniDeleteAllocator, stream.avstrminideleteallocator
f1_keywords:
 - "ks/AVStrMiniDeleteAllocator"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ks.h
api_name:
- AVStrMiniDeleteAllocator
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNKSDELETEALLOCATOR callback function


## -description


An AVStream minidriver's <i>AVStrMiniDeleteAllocator</i> routine deletes the allocator that is associated with a pin.


## -parameters




### -param Context [in]

Pointer to the allocator's context structure created by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkspininitializeallocator">AVStrMiniInitializeAllocator</a>.


## -remarks



The minidriver specifies this routine's address in the <b>DeleteAllocator</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksallocator_dispatch">KSALLOCATOR_DISPATCH</a> structure. The minidriver passes this structure to the class driver in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a>.

Once this function is called, AVStream will no longer use the allocator to allocate and free memory. This handler should release all system resources reserved by the allocator.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ks-allocators">KS Allocators</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkspininitializeallocator">AVStrMiniInitializeAllocator</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksallocator_dispatch">KSALLOCATOR_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a>
 

 

