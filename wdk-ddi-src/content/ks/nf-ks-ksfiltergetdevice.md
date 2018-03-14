---
UID: NF:ks.KsFilterGetDevice
title: KsFilterGetDevice function
author: windows-driver-content
description: The KsFilterGetDevice function returns the AVStream device to which Filter belongs.
old-location: stream\ksfiltergetdevice.htm
old-project: stream
ms.assetid: f3abb5e4-6711-47bb-82b5-7ef838d49258
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsFilterGetDevice, KsFilterGetDevice function [Streaming Media Devices], avfunc_279c1429-d19f-426c-a1e3-8507f97092ae.xml, ks/KsFilterGetDevice, stream.ksfiltergetdevice
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KsFilterGetDevice
product: Windows
targetos: Windows
req.typenames: 
---

# KsFilterGetDevice function


## -description


The<b> KsFilterGetDevice </b>function returns the AVStream device to which <i>Filter</i> belongs.


## -syntax


````
PKSDEVICE __inline KsFilterGetDevice(
  _In_ PKSFILTER Filter
);
````


## -parameters




### -param Filter [in]

A pointer to the <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure for which to find the owning AVStream device.


## -returns



<b>KsFilterGetDevice</b> returns a pointer to the AVStream <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure to which <i>Filter</i> belongs.




## -remarks



This call is an inline function call to <a href="..\ks\nf-ks-ksgetdevice.md">KsGetDevice</a>.




## -see-also

<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>



<a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>



<a href="..\ks\nf-ks-ksgetdevice.md">KsGetDevice</a>



 

 


