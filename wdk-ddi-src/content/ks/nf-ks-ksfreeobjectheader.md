---
UID: NF:ks.KsFreeObjectHeader
title: KsFreeObjectHeader function
author: windows-driver-content
description: The KsFreeObjectHeader function cleans up and frees a previously allocated object header.
old-location: stream\ksfreeobjectheader.htm
old-project: stream
ms.assetid: 59ca5035-f4d8-4a9c-a298-c8dca604f4db
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KsFreeObjectHeader, KsFreeObjectHeader, ksfunc_11097907-6879-43bb-879b-b74eb13d6109.xml, stream.ksfreeobjectheader, KsFreeObjectHeader function [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsFreeObjectHeader
product: Windows
targetos: Windows
req.typenames: 
---

# KsFreeObjectHeader function


## -description


The <b>KsFreeObjectHeader</b> function cleans up and frees a previously allocated object header.


## -syntax


````
VOID KsFreeObjectHeader(
  _In_ KSOBJECT_HEADER Header
);
````


## -parameters




#### - Header [in]

Points to the object header to free.


## -returns


None



## -see-also

<a href="..\ks\nf-ks-ksallocateobjectheader.md">KsAllocateObjectHeader</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFreeObjectHeader function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

