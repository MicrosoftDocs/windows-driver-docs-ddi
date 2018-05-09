---
UID: NF:ks.KsFilterFactoryGetDevice
title: KsFilterFactoryGetDevice function
author: windows-driver-content
description: The KsFilterFactoryGetDevice function returns the AVStream device to which FilterFactory belongs.
old-location: stream\ksfilterfactorygetdevice.htm
old-project: stream
ms.assetid: e5b7b014-3e06-49f2-8ccd-45d74592e349
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsFilterFactoryGetDevice, KsFilterFactoryGetDevice function [Streaming Media Devices], avfunc_1e2ec536-69a1-4606-9d99-ebdebd25c89a.xml, ks/KsFilterFactoryGetDevice, stream.ksfilterfactorygetdevice
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
-	KsFilterFactoryGetDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFilterFactoryGetDevice function


## -description


The<b> KsFilterFactoryGetDevice </b>function returns the AVStream device to which <i>FilterFactory </i>belongs.


## -parameters




### -param FilterFactory [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a> structure for which to find the corresponding AVStream device.


## -returns



Returns a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a> structure representing the AVStream device to which <i>FilterFactory</i> belongs.




## -remarks



This call is an inline function call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff562615">KsGetDevice</a>.

For more information about the AVStream object hierarchy, see  <a href="https://msdn.microsoft.com/305039fe-0a00-4f3e-ae1a-61c50a2f2fb3">AVStream Overview</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562615">KsGetDevice</a>
 

 

