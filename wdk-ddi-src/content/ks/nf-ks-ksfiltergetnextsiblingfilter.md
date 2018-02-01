---
UID: NF:ks.KsFilterGetNextSiblingFilter
title: KsFilterGetNextSiblingFilter function
author: windows-driver-content
description: The KsFilterGetNextSiblingFilter function returns the next instantiated filter belonging to the parent filter factory of Filter.
old-location: stream\ksfiltergetnextsiblingfilter.htm
old-project: stream
ms.assetid: 0b0a306a-6066-4a7d-ae2d-12eb8bb3adc0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsFilterGetNextSiblingFilter, avfunc_bda9f36a-10d4-4de3-88b2-a358aad4fd04.xml, ks/KsFilterGetNextSiblingFilter, stream.ksfiltergetnextsiblingfilter, KsFilterGetNextSiblingFilter function [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KsFilterGetNextSiblingFilter
product: Windows
targetos: Windows
req.typenames: 
---

# KsFilterGetNextSiblingFilter function


## -description


The<b> KsFilterGetNextSiblingFilter</b> function returns the next instantiated filter belonging to the parent filter factory of <i>Filter</i>.


## -syntax


````
PKSFILTER __inline KsFilterGetNextSiblingFilter(
  _In_ PKSFILTER Filter
);
````


## -parameters




### -param Filter [in]

A pointer to the <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure for which to find the next sibling filter.


## -returns


<b>KsFilterGetNextSiblingFilter</b> returns a pointer to the next sibling <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure of <i>Filter</i>. If no such instantiated filter exists, it returns <b>NULL</b>.



## -remarks


This call is an inline function call to <a href="..\ks\nf-ks-ksgetnextsibling.md">KsGetNextSibling</a>. Note that the object hierarchy is only guaranteed stable while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.



## -see-also

<a href="..\ks\nf-ks-ksfilterfactorygetfirstchildfilter.md">KsFilterFactoryGetFirstChildFilter</a>

<a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>

<a href="..\ks\nf-ks-ksgetnextsibling.md">KsGetNextSibling</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterGetNextSiblingFilter function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

