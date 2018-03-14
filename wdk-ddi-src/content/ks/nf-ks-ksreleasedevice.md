---
UID: NF:ks.KsReleaseDevice
title: KsReleaseDevice function
author: windows-driver-content
description: The KsReleaseDevice function releases the device mutex and exits the critical region.
old-location: stream\ksreleasedevice.htm
old-project: stream
ms.assetid: 47692ac1-969a-4f6f-a2e1-008b82ac1429
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsReleaseDevice, KsReleaseDevice function [Streaming Media Devices], avfunc_47876dbc-0dea-459f-96f7-81790d245745.xml, ks/KsReleaseDevice, stream.ksreleasedevice
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
-	KsReleaseDevice
product: Windows
targetos: Windows
req.typenames: 
---

# KsReleaseDevice function


## -description


The<b> KsReleaseDevice</b> function releases the device mutex and exits the critical region.


## -syntax


````
void KsReleaseDevice(
  _In_ PKSDEVICE Device
);
````


## -parameters




### -param Device [in]

A pointer to a <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure representing the AVStream device for which to release synchronous control.


## -returns



None




## -remarks



<b>KsReleaseDevice </b>is used by a client that has finished accessing the device in a synchronous manner following a previous call to <a href="..\ks\nf-ks-ksacquiredevice.md">KsAcquireDevice</a>.

For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>. 




## -see-also

<a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a>



<a href="..\ks\nf-ks-ksacquiredevice.md">KsAcquireDevice</a>



 

 


