---
UID: NC:ks.PFNKSDEFAULTALLOCATE
title: PFNKSDEFAULTALLOCATE
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniAllocate routine allocates a frame using the allocator specified in the Context parameter.
old-location: stream\avstrminiallocate.htm
old-project: stream
ms.assetid: f718e788-306a-4dbc-96cb-a81299aafe1d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.avstrminiallocate, AVStrMiniAllocate, AVStrMiniAllocate routine [Streaming Media Devices], AVStrMiniAllocate, PFNKSDEFAULTALLOCATE, PFNKSDEFAULTALLOCATE, ks/AVStrMiniAllocate, avstclbk_3ed4229c-f462-4b86-9dd4-374275f10c24.xml
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
-	AVStrMiniAllocate
product: Windows
targetos: Windows
req.typenames: KEYWORDSELECTOR
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

<a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a>

<a href="..\ks\nc-ks-pfnkspininitializeallocator.md">AVStrMiniInitializeAllocator</a>

<a href="..\ks\ns-ks-_ksallocator_dispatch.md">KSALLOCATOR_DISPATCH</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSDEFAULTALLOCATE routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

