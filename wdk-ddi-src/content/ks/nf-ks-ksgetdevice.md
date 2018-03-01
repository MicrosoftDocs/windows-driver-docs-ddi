---
UID: NF:ks.KsGetDevice
title: KsGetDevice function
author: windows-driver-content
description: The KsGetDevice function returns the AVStream device structure to which Object belongs.
old-location: stream\ksgetdevice.htm
old-project: stream
ms.assetid: 27fb223f-9e6b-42af-b3d8-1018dc5416c2
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGetDevice, KsGetDevice function [Streaming Media Devices], avfunc_8459c499-365e-4cd4-927c-b359792937b0.xml, ks/KsGetDevice, stream.ksgetdevice
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
-	KsGetDevice
product: Windows
targetos: Windows
req.typenames: 
---

# KsGetDevice function


## -description


The<b> KsGetDevice</b> function returns the AVStream device structure to which <i>Object </i>belongs.


## -syntax


````
PKSDEVICE KsGetDevice(
  _In_ PVOID Object
);
````


## -parameters




### -param Object [in]

The object to query for the device to which it belongs.


## -returns



<b>KsGetDevice</b> returns a pointer to a <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure that is the AVStream device to which <i>Object</i> belongs.




## -remarks



<i>Object</i> should be one of: PKSPIN, PKSFILTER, or PKSFILTERFACTORY. Callers must perform appropriate typecasting to PVOID.

Minidrivers typically do not call this function directly. There are a number of functions that perform inline calls to <b>KsGetDevice</b> and that perform typecasting automatically: <a href="..\ks\nf-ks-ksfilterfactorygetdevice.md">KsFilterFactoryGetDevice</a>, <a href="..\ks\nf-ks-ksfiltergetdevice.md">KsFilterGetDevice</a>, and <a href="..\ks\nf-ks-kspingetdevice.md">KsPinGetDevice</a>.




## -see-also

<a href="..\ks\nf-ks-ksfilterfactorygetdevice.md">KsFilterFactoryGetDevice</a>



<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>



<a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>



<a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a>



<a href="..\ks\nf-ks-ksfiltergetdevice.md">KsFilterGetDevice</a>



<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>



<a href="..\ks\nf-ks-kspingetdevice.md">KsPinGetDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetDevice function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

