---
UID: NF:ks.KsGetDevice
title: KsGetDevice function
author: windows-driver-content
description: The KsGetDevice function returns the AVStream device structure to which Object belongs.
old-location: stream\ksgetdevice.htm
old-project: stream
ms.assetid: 27fb223f-9e6b-42af-b3d8-1018dc5416c2
ms.author: windowsdriverdev
ms.date: 4/23/2018
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


## -parameters




### -param Object [in]

The object to query for the device to which it belongs.


## -returns



<b>KsGetDevice</b> returns a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a> structure that is the AVStream device to which <i>Object</i> belongs.




## -remarks



<i>Object</i> should be one of: PKSPIN, PKSFILTER, or PKSFILTERFACTORY. Callers must perform appropriate typecasting to PVOID.

Minidrivers typically do not call this function directly. There are a number of functions that perform inline calls to <b>KsGetDevice</b> and that perform typecasting automatically: <a href="https://msdn.microsoft.com/library/windows/hardware/ff562532">KsFilterFactoryGetDevice</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff562544">KsFilterGetDevice</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff563511">KsPinGetDevice</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562532">KsFilterFactoryGetDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562544">KsFilterGetDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563511">KsPinGetDevice</a>
 

 

