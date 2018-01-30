---
UID: NF:ksproxy.IKsAllocator.KsGetAllocatorMode
title: IKsAllocator::KsGetAllocatorMode method
author: windows-driver-content
description: Returns the mode in which an allocator allocates memory.
old-location: stream\iksallocator_ksgetallocatormode.htm
old-project: stream
ms.assetid: 47B51B6F-555A-4A1E-AA25-7E94DC0060CC
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IKsAllocator interface [Streaming Media Devices], KsGetAllocatorMode method, KsGetAllocatorMode method [Streaming Media Devices], IKsAllocator interface, IKsAllocator, IKsAllocator::KsGetAllocatorMode, KsGetAllocatorMode method [Streaming Media Devices], stream.iksallocator_ksgetallocatormode, KsGetAllocatorMode, ksproxy/IKsAllocator::KsGetAllocatorMode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Windows
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
req.lib: ksproxy.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ksproxy.h
apiname:
-	IKsAllocator.KsGetAllocatorMode
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsAllocator::KsGetAllocatorMode method


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Returns the mode in which an allocator allocates memory.


## -syntax


````
HRESULT KsGetAllocatorMode(
    
);
````


## -parameters





## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



## -see-also

<a href="..\ksproxy\nn-ksproxy-iksallocator.md">IKsAllocator</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsAllocator::KsGetAllocatorMode method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

