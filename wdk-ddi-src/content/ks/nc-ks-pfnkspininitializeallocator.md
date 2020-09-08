---
UID: NC:ks.PFNKSPININITIALIZEALLOCATOR
title: PFNKSPININITIALIZEALLOCATOR (ks.h)
description: An AVStream minidriver's AVStrMiniInitializeAllocator routine initializes an allocator that will be associated with a pin.
old-location: stream\avstrminiinitializeallocator.htm
tech.root: stream
ms.assetid: 9c6d3856-702c-416b-a5d2-b3578a55bbcd
ms.date: 04/23/2018
keywords: ["PFNKSPININITIALIZEALLOCATOR callback function"]
ms.keywords: AVStrMiniInitializeAllocator, AVStrMiniInitializeAllocator routine [Streaming Media Devices], PFNKSPININITIALIZEALLOCATOR, avstclbk_979c0a29-7e4b-463c-8ff3-62124b0d49d1.xml, ks/AVStrMiniInitializeAllocator, stream.avstrminiinitializeallocator
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNKSPININITIALIZEALLOCATOR
 - ks/PFNKSPININITIALIZEALLOCATOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - AVStrMiniInitializeAllocator
---

# PFNKSPININITIALIZEALLOCATOR callback function


## -description

An AVStream minidriver's <i>AVStrMiniInitializeAllocator</i> routine initializes an allocator that will be associated with a pin.

## -parameters

### -param Pin 

[in]
Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure describing the pin with which the allocator is to be associated.

### -param AllocatorFraming 

[in]
Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing">KSALLOCATOR_FRAMING</a> structure describing the framing requirements that the allocator should use.

### -param Context 

[out]
Pointer to a context for the allocator that will be passed as a parameter to the other routines for this structure. For example, the driver could store pin or allocator framing structures for later reference by the other callback routines. Note that other routines for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksallocator_dispatch">KSALLOCATOR_DISPATCH</a> must have at least an indirect way of referencing <i>Pin</i>. (For instance, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnksdefaultallocate">AVStrMiniAllocate</a> will need to be able to access the <i>AllocatorFraming</i> information for <i>Pin</i>, and <i>Context</i> is the only parameter that AVStream will pass it.)

## -returns

<i>AVStrMiniInitializeAllocator</i> should return STATUS_SUCCESS or the error code that it received attempting to create the allocator.

## -remarks

The minidriver specifies this routine's address in the <b>InitializeAllocator</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksallocator_dispatch">KSALLOCATOR_DISPATCH</a> structure. The minidriver passes this structure to the class driver in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a>.

Note that kernel-mode allocators cannot allocate frames that could eventually reach user mode.

AVStream calls <i>AVStrMiniInitializeAllocator</i> to initialize the given allocator. The handler for this routine should prepare to handle memory allocation and free requests.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ks-allocators">KS Allocators</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnksdeleteallocator">AVStrMiniDeleteAllocator</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksallocator_dispatch">KSALLOCATOR_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing">KSALLOCATOR_FRAMING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a>

