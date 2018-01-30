---
UID: NF:ks.KsDiscard
title: KsDiscard macro
author: windows-driver-content
description: The KsDiscard macro removes a given item from an object bag.
old-location: stream\ksdiscard.htm
old-project: stream
ms.assetid: cbd1cd9b-c3bd-4827-88e6-4b80d6ba7320
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ksdiscard, ks/KsDiscard, avfunc_645e5574-6c6b-4336-87fe-fe777f7d1c91.xml, KsDiscard, KsDiscard function [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsDiscard
product: Windows
targetos: Windows
req.typenames: 
---

# KsDiscard macro


## -description


The<b> KsDiscard </b>macro removes a given item from an object bag.


## -syntax


````
ULONG KsDiscard(
  _In_ KSxxx Object,
  _In_ PVOID Pointer
);
````


## -parameters




### -param Object [in]

The item pointed to by <i>Pointer</i> is removed from the object bag associated with this object. Can be of type <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>, <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a>, <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>, or <a href="..\ks\ns-ks-_kspin.md">KSPIN</a>.


### -param Pointer [in]

A pointer to the item to be removed from the requested object's bag.


## -remarks


This function is implemented as a C-style preprocessing macro in the <i>Ks.h</i> header.

<b>KsDiscard</b> calls <a href="..\ks\nf-ks-ksremoveitemfromobjectbag.md">KsRemoveItemFromObjectBag</a>, passing the object bag associated with <i>Object</i> (<i>Object -&gt; Bag</i>), the item specified by <i>Pointer</i>, and <b>TRUE</b> for the <i>Free</i> parameter. 



## -see-also

<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>

<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>

<a href="..\ks\nf-ks-ksremoveitemfromobjectbag.md">KsRemoveItemFromObjectBag</a>

<a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>

<a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDiscard function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

