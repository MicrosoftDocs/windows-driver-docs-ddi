---
UID: NF:ks.KsFilterFactoryRegisterAggregatedClientUnknown
title: KsFilterFactoryRegisterAggregatedClientUnknown function (ks.h)
description: This inline function is a wrapper for KsRegisterAggregatedClientUnknown.
old-location: stream\ksfilterfactoryregisteraggregatedclientunknown.htm
tech.root: stream
ms.assetid: 7750a0f5-f38d-4530-81dc-589a1c2009ca
ms.date: 04/23/2018
ms.keywords: KsFilterFactoryRegisterAggregatedClientUnknown, KsFilterFactoryRegisterAggregatedClientUnknown function [Streaming Media Devices], avfunc_03ec0abd-d481-4b97-b8ab-6be504e95a55.xml, ks/KsFilterFactoryRegisterAggregatedClientUnknown, stream.ksfilterfactoryregisteraggregatedclientunknown
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KsFilterFactoryRegisterAggregatedClientUnknown
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsFilterFactoryRegisterAggregatedClientUnknown function


## -description


This inline function is a wrapper for <a href="https://msdn.microsoft.com/library/windows/hardware/ff566767">KsRegisterAggregatedClientUnknown</a>.


## -parameters




### -param FilterFactory [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a> structure that represents the specified AVStream filter factory.


### -param ClientUnknown [in]

A pointer to the client <b>IUnknown</b> interface.


## -returns



<b>KsFilterFactoryRegisterAggregatedClientUnknown</b> returns a pointer to the <b>IUnknown</b> interface of the newly created aggregate object.




## -remarks



Note that this inline function only performs a typecast and then calls <b>KsRegisterAggregatedClientUnknown</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566767">KsRegisterAggregatedClientUnknown</a>
 

 

