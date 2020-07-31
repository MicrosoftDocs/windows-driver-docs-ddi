---
UID: NF:ks.KsPinGetOuterUnknown
title: KsPinGetOuterUnknown function (ks.h)
description: The KsPinGetOuterUnknown function returns the outer IUnknown of the pin specified by Pin.
old-location: stream\kspingetouterunknown.htm
tech.root: stream
ms.assetid: 58b14ddd-6698-487a-925d-7d559057e55d
ms.date: 04/23/2018
keywords: ["KsPinGetOuterUnknown function"]
ms.keywords: KsPinGetOuterUnknown, KsPinGetOuterUnknown function [Streaming Media Devices], avfunc_6a9c21cd-38ab-4277-8379-346af4c9c4c9.xml, ks/KsPinGetOuterUnknown, stream.kspingetouterunknown
f1_keywords:
 - "ks/KsPinGetOuterUnknown"
 - "KsPinGetOuterUnknown"
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
- KsPinGetOuterUnknown
targetos: Windows
req.typenames: 
---

# KsPinGetOuterUnknown function


## -description


The<b> KsPinGetOuterUnknown</b> function returns the outer <b>IUnknown</b> of the pin specified by <i>Pin</i>.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure for which to return the outer <b>IUnknown</b>.


## -returns



<b>KsPinGetOuterUnknown</b> returns a pointer to the outer <b>IUnknown</b> interface of <i>Pin</i>. This can subsequently be used to query for other interfaces.




## -remarks



<b>KsPinGetOuterUnknown</b> is an inline function call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetouterunknown">KsGetOuterUnknown</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avstream-overview">AVStream Overview</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-ikscontrol">IKsControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksdevicegetouterunknown">KsDeviceGetOuterUnknown</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfilterfactorygetouterunknown">KsFilterFactoryGetOuterUnknown</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergetouterunknown">KsFilterGetOuterUnknown</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetouterunknown">KsGetOuterUnknown</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksregisteraggregatedclientunknown">KsRegisterAggregatedClientUnknown</a>
 

 

