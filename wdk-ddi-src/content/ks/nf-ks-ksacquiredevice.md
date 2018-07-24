---
UID: NF:ks.KsAcquireDevice
title: KsAcquireDevice function
author: windows-driver-content
description: The KsAcquireDevice function gains synchronous access for Device by acquiring the device mutex.
old-location: stream\ksacquiredevice.htm
tech.root: stream
ms.assetid: c486351a-b5a6-4a67-826d-6f66d04518b3
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsAcquireDevice, KsAcquireDevice function [Streaming Media Devices], avfunc_396e6da2-9423-43ae-8a2b-24655a43037b.xml, ks/KsAcquireDevice, stream.ksacquiredevice
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
-	KsAcquireDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsAcquireDevice function


## -description


The<b> KsAcquireDevice</b> function gains synchronous access for <i>Device</i> by acquiring the device mutex.


## -parameters




### -param Device [in]

An AVStream device for which synchronous control should be acquired.


## -returns



None




## -remarks



For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566783">KsReleaseDevice</a>
 

 

