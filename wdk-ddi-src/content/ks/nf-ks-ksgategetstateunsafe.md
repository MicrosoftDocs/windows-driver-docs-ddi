---
UID: NF:ks.KsGateGetStateUnsafe
title: KsGateGetStateUnsafe function (ks.h)
description: The KsGateGetStateUnsafe function returns the state of the given gate (open or closed) in an unsafe manner, that is without regard to synchronization.
old-location: stream\ksgategetstateunsafe.htm
tech.root: stream
ms.assetid: f5976125-4ff4-48c2-a5c7-8e9fb2f8a0c9
ms.date: 04/23/2018
ms.keywords: KsGateGetStateUnsafe, KsGateGetStateUnsafe function [Streaming Media Devices], avfunc_1f18b601-daaf-4df2-98c2-a91646f84c0d.xml, ks/KsGateGetStateUnsafe, stream.ksgategetstateunsafe
ms.topic: function
f1_keywords:
 - "ks/KsGateGetStateUnsafe"
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KsGateGetStateUnsafe
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGateGetStateUnsafe function


## -description


The<b> KsGateGetStateUnsafe</b> function returns the state of the given gate (open or closed)  in an unsafe manner, that is <i>without regard to synchronization</i>.


## -parameters




### -param Gate [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksgate">KSGATE</a> structure representing the gate for which to return the state.


## -returns



This call returns <b>TRUE</b> if the gate is open and <b>FALSE</b> if the gate is closed.




## -remarks



Because <b>KsGateGetStateUnsafe</b> does not handle synchronization, it is possible to get a result that is not consistent with the state of the gate if the gate is in mid-transition from one state to another at the time of the call.

Consider a situation in which the output of gate A is connected as an input to gate B. A transitions to closed, causing B to transition from open to closed. If, at the same time, another thread calls <b>KsGateGetStateUnsafe</b> between the time A closes and the time B closes, the routine still returns that B was open.

<b>KsGateGetStateUnsafe</b> returns whether <i>Gate->Count</i> is greater than zero. The function does not use any interlocked functions to do this. Thus, the call is performed without regard to synchronization.



