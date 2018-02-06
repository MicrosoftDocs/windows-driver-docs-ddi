---
UID: NC:ks.PFNKSDELETEALLOCATOR
title: PFNKSDELETEALLOCATOR
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniDeleteAllocator routine deletes the allocator that is associated with a pin.
old-location: stream\avstrminideleteallocator.htm
old-project: stream
ms.assetid: 867da1f8-061b-4fc1-8e20-3ebc43300f15
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.avstrminideleteallocator, AVStrMiniDeleteAllocator, AVStrMiniDeleteAllocator routine [Streaming Media Devices], AVStrMiniDeleteAllocator, PFNKSDELETEALLOCATOR, PFNKSDELETEALLOCATOR, ks/AVStrMiniDeleteAllocator, avstclbk_32e3c0fd-c437-45e0-8e5e-72f2f628ee51.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ks.h
apiname:
-	AVStrMiniDeleteAllocator
product: Windows
targetos: Windows
req.typenames: KEYWORDSELECTOR
---

# PFNKSDELETEALLOCATOR callback


## -description


An AVStream minidriver's <i>AVStrMiniDeleteAllocator</i> routine deletes the allocator that is associated with a pin.


## -prototype


````
PFNKSDELETEALLOCATOR AVStrMiniDeleteAllocator;

VOID AVStrMiniDeleteAllocator(
  _In_ PVOID Context
)
{ ... }
````


## -parameters




### -param Context [in]

Pointer to the allocator's context structure created by <a href="..\ks\nc-ks-pfnkspininitializeallocator.md">AVStrMiniInitializeAllocator</a>.


## -returns


None



## -remarks


The minidriver specifies this routine's address in the <b>DeleteAllocator</b> member of its <a href="..\ks\ns-ks-_ksallocator_dispatch.md">KSALLOCATOR_DISPATCH</a> structure. The minidriver passes this structure to the class driver in <a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a>.

Once this function is called, AVStream will no longer use the allocator to allocate and free memory. This handler should release all system resources reserved by the allocator.

For more information, see <a href="https://msdn.microsoft.com/07812703-a66f-450a-b28e-4cf765267c4a">KS Allocators</a>.



## -see-also

<a href="..\ks\nc-ks-pfnkspininitializeallocator.md">AVStrMiniInitializeAllocator</a>

<a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a>

<a href="..\ks\ns-ks-_ksallocator_dispatch.md">KSALLOCATOR_DISPATCH</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSDELETEALLOCATOR routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

