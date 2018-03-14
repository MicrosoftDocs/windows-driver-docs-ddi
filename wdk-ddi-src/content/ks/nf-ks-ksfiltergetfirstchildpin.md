---
UID: NF:ks.KsFilterGetFirstChildPin
title: KsFilterGetFirstChildPin function
author: windows-driver-content
description: The KsFilterGetFirstChildPin function returns the first instantiated pin of type PinID on the filter specified by Filter.
old-location: stream\ksfiltergetfirstchildpin.htm
old-project: stream
ms.assetid: b026908a-51d4-45a8-9c0e-1c163563bfbf
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsFilterGetFirstChildPin, KsFilterGetFirstChildPin function [Streaming Media Devices], avfunc_303477ee-598b-4b5b-baae-1e520c154e99.xml, ks/KsFilterGetFirstChildPin, stream.ksfiltergetfirstchildpin
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsFilterGetFirstChildPin
product: Windows
targetos: Windows
req.typenames: 
---

# KsFilterGetFirstChildPin function


## -description


The<b> KsFilterGetFirstChildPin</b> function returns the first instantiated pin of type <i>PinID</i> on the filter specified by <i>Filter</i>.


## -syntax


````
PKSPIN KsFilterGetFirstChildPin(
  _In_ PKSFILTER Filter,
  _In_ ULONG     PinId
);
````


## -parameters




### -param Filter [in]

A pointer to the <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure to query for instantiated pins.


### -param PinId [in]

The numeric ID of the pin type for which to find the first instantiated member.


## -returns



<b>KsFilterGetFirstChildPin</b> returns a pointer to the first instantiated <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure of type <i>PinID</i> on the specified filter.




## -remarks



Note that the object hierarchy is guaranteed stable only while the appropriate mutex is held, in this case the filter control mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.




## -see-also

<a href="..\ks\nf-ks-kspingetnextsiblingpin.md">KsPinGetNextSiblingPin</a>



<a href="..\ks\nf-ks-ksfiltergetchildpincount.md">KsFilterGetChildPinCount</a>



<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>



 

 


