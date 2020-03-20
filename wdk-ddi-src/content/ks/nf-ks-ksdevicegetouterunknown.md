---
UID: NF:ks.KsDeviceGetOuterUnknown
title: KsDeviceGetOuterUnknown function (ks.h)
description: The KsDeviceGetOuterUnknown function returns the outer IUnknown of the AVStream device specified by Device.
old-location: stream\ksdevicegetouterunknown.htm
tech.root: stream
ms.assetid: a63cdc50-6bbb-4bff-8536-0bf31fed01de
ms.date: 04/23/2018
keywords: ["KsDeviceGetOuterUnknown function"]
ms.keywords: KsDeviceGetOuterUnknown, KsDeviceGetOuterUnknown function [Streaming Media Devices], avfunc_c1b85ab7-92b9-4c7c-a9c8-0cf1f9e93458.xml, ks/KsDeviceGetOuterUnknown, stream.ksdevicegetouterunknown
f1_keywords:
 - "ks/KsDeviceGetOuterUnknown"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KsDeviceGetOuterUnknown
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsDeviceGetOuterUnknown function


## -description


The<b> KsDeviceGetOuterUnknown</b> function returns the outer <b>IUnknown</b> of the AVStream device specified by <i>Device</i>.


## -parameters




### -param Device [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a> structure for which to get the outer unknown interface.


## -returns



Returns a pointer to an outer <b>IUnknown</b> of <i>Device</i>. This interface can then be used to query for other interfaces.




## -remarks



This call is an inline function call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetouterunknown">KsGetOuterUnknown</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-ikscontrol">IKsControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterfactorygetouterunknown">KsFilterFactoryGetOuterUnknown</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergetouterunknown">KsFilterGetOuterUnknown</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetouterunknown">KsGetOuterUnknown</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetouterunknown">KsPinGetOuterUnknown</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksregisteraggregatedclientunknown">KsRegisterAggregatedClientUnknown</a>
 

 

