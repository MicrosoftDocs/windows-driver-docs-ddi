---
UID: NF:ks.KsPinRegisterAggregatedClientUnknown
title: KsPinRegisterAggregatedClientUnknown function (ks.h)
description: This inline function is a wrapper for KsRegisterAggregatedClientUnknown.
old-location: stream\kspinregisteraggregatedclientunknown.htm
tech.root: stream
ms.assetid: 302d87be-a276-49ea-98f2-89e1f231c3c6
ms.date: 04/23/2018
ms.keywords: KsPinRegisterAggregatedClientUnknown, KsPinRegisterAggregatedClientUnknown function [Streaming Media Devices], avfunc_688a6c60-58c8-4e65-a3bc-d68e713ca3fc.xml, ks/KsPinRegisterAggregatedClientUnknown, stream.kspinregisteraggregatedclientunknown
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
-	KsPinRegisterAggregatedClientUnknown
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinRegisterAggregatedClientUnknown function


## -description


This inline function is a wrapper for <a href="https://msdn.microsoft.com/library/windows/hardware/ff566767">KsRegisterAggregatedClientUnknown</a>.


## -parameters




### -param Pin [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure.


### -param ClientUnknown [in]

A pointer to an <b>IUnknown</b> interface.


## -returns



<b>KsPinRegisterAggregatedClientUnknown</b> returns the newly created aggregate object.




## -remarks



This inline function only performs a typecast and then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff566767">KsRegisterAggregatedClientUnknown</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566767">KsRegisterAggregatedClientUnknown</a>
 

 

