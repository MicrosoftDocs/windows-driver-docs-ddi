---
UID: NC:ks.PFNKSITEMFREECALLBACK
title: PFNKSITEMFREECALLBACK
author: windows-driver-content
description: A streaming minidriver's KStrItemFreeCallback routine is called to free a previously allocated create item. KStrItemFreeCallback allows the minidriver to perform any cleanup, including flushing security descriptor changes, if necessary.
old-location: stream\kstritemfreecallback.htm
old-project: stream
ms.assetid: c97bb216-a53b-47c7-9be2-2364604b4cf8
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.kstritemfreecallback, KStrItemFreeCallback routine [Streaming Media Devices], KStrItemFreeCallback, PFNKSITEMFREECALLBACK, PFNKSITEMFREECALLBACK, ks/KStrItemFreeCallback, ksfunc_3d98c1cb-4984-4d82-8e58-181445f1feca.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
-	KStrItemFreeCallback
product: Windows
targetos: Windows
req.typenames: KEYWORDSELECTOR
---

# PFNKSITEMFREECALLBACK callback


## -description


A streaming minidriver's <i>KStrItemFreeCallback</i> routine is called to free a previously allocated create item. <i>KStrItemFreeCallback</i> allows the minidriver to perform any cleanup, including flushing security descriptor changes, if necessary.


## -prototype


````
PFNKSITEMFREECALLBACK KStrItemFreeCallback;

VOID KStrItemFreeCallback(
  _In_ PKSOBJECT_CREATE_ITEM CreateItem
)
{ ... }
````


## -parameters




### -param CreateItem [in]

Specifies a create item that was previously allocated by <a href="..\ks\nf-ks-ksallocateobjectcreateitem.md">KsAllocateObjectCreateItem</a>.


## -returns


Returns STATUS_SUCCESS if the passed in create item was successfully freed, or the error code that was returned from the minidriver's attempt to free the create item in <i>KStrItemFreeCallback</i>.



## -remarks


The <i>Context</i> parameter of the <a href="..\ks\ns-ks-ksobject_create_item.md">KSOBJECT_CREATE_ITEM</a> structure must contain sufficient information to perform cleanup for the create item.

The <i>Flags</i> member of the KSOBJECT_CREATE_ITEM structure indicates if it is necessary to flush security descriptor changes.



## -see-also

<a href="..\ks\nf-ks-ksallocateobjectcreateitem.md">KsAllocateObjectCreateItem</a>

<a href="..\ks\ns-ks-ksobject_create_item.md">KSOBJECT_CREATE_ITEM</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KStrItemFreeCallback routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

