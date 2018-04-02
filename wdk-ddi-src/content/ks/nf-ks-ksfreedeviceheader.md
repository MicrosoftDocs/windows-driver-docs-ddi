---
UID: NF:ks.KsFreeDeviceHeader
title: KsFreeDeviceHeader function
author: windows-driver-content
description: The KsFreeDeviceHeader function cleans up and frees a previously allocated device header.
old-location: stream\ksfreedeviceheader.htm
old-project: stream
ms.assetid: b7e30dde-ace5-47f0-a1e8-b8337ada1550
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsFreeDeviceHeader, KsFreeDeviceHeader function [Streaming Media Devices], ks/KsFreeDeviceHeader, ksfunc_25c133a5-3c21-476f-84f5-b208284d9234.xml, stream.ksfreedeviceheader
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsFreeDeviceHeader
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFreeDeviceHeader function


## -description


The <b>KsFreeDeviceHeader</b> function cleans up and frees a previously allocated device header.


## -parameters




### -param Header [in]

Indicates the device header to free that had been previously allocated by <b>KsAllocateDeviceHeader</b>.


## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560958">KsAllocateDeviceHeader</a>
 

 

