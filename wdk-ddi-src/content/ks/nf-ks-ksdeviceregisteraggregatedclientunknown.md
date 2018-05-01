---
UID: NF:ks.KsDeviceRegisterAggregatedClientUnknown
title: KsDeviceRegisterAggregatedClientUnknown function
author: windows-driver-content
description: This inline function is a wrapper for KsRegisterAggregatedClientUnknown.
old-location: stream\ksdeviceregisteraggregatedclientunknown.htm
old-project: stream
ms.assetid: d4d3f653-cfdc-4567-97bc-def26484ed9f
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsDeviceRegisterAggregatedClientUnknown, KsDeviceRegisterAggregatedClientUnknown function [Streaming Media Devices], avfunc_3e7aa517-80e8-498c-939d-1769393479fb.xml, ks/KsDeviceRegisterAggregatedClientUnknown, stream.ksdeviceregisteraggregatedclientunknown
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KsDeviceRegisterAggregatedClientUnknown
product: Windows
targetos: Windows
req.typenames: 
---

# KsDeviceRegisterAggregatedClientUnknown function


## -description


This inline function is a wrapper for <a href="https://msdn.microsoft.com/library/windows/hardware/ff566767">KsRegisterAggregatedClientUnknown</a>.


## -parameters




### -param Device [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a> structure representing the specified AVStream device.


### -param ClientUnknown [in]

A pointer to the client's undelegated <b>IUnknown</b> interface.


## -returns



Returns the newly created aggregate object.




## -remarks



This inline function performs a typecast and then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff566767">KsRegisterAggregatedClientUnknown</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566767">KsRegisterAggregatedClientUnknown</a>
 

 

