---
UID: NC:ks.PFNKSDEFAULTALLOCATE
title: PFNKSDEFAULTALLOCATE
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniAllocate routine allocates a frame using the allocator specified in the Context parameter.
old-location: stream\avstrminiallocate.htm
old-project: stream
ms.assetid: f718e788-306a-4dbc-96cb-a81299aafe1d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AVStrMiniAllocate, AVStrMiniAllocate routine [Streaming Media Devices], PFNKSDEFAULTALLOCATE, avstclbk_3ed4229c-f462-4b86-9dd4-374275f10c24.xml, ks/AVStrMiniAllocate, stream.avstrminiallocate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ks.h
api_name:
-	AVStrMiniAllocate
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---

# PFNKSDEFAULTALLOCATE callback


## -description


An AVStream minidriver's <i>AVStrMiniAllocate</i> routine allocates a frame using the allocator specified in the <i>Context</i> parameter.


## -prototype


````
PFNKSDEFAULTALLOCATE AVStrMiniAllocate;

PVOID AVStrMiniAllocate(
  _In_ PVOID Context
)
{ ... }
````


## -parameters




### -param Context [in]

Pointer to the allocator's context structure created in <i>AVStrMiniInitializeAllocator</i>.


## -returns



<b>Allocate</b> returns a pointer to the newly allocated memory. Return <b>NULL</b> if the attempt to allocate memory failed.




## -remarks



The minidriver specifies this routine's address in the <b>Allocate</b> member of its <a href="..\ks\ns-ks-_ksallocator_dispatch.md">KSALLOCATOR_DISPATCH</a> structure. The minidriver passes this structure to the class driver in <a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a>.

AVStream calls this routine to allocate a frame. The handler should allocate a frame as described by the allocator framing context passed into the initialization dispatch.

For more information, see <a href="https://msdn.microsoft.com/07812703-a66f-450a-b28e-4cf765267c4a">KS Allocators</a>.




## -see-also

<a href="..\ks\nc-ks-pfnkspininitializeallocator.md">AVStrMiniInitializeAllocator</a>



<a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a>



<a href="..\ks\ns-ks-_ksallocator_dispatch.md">KSALLOCATOR_DISPATCH</a>



 

 


