---
UID: NF:ks.KsGateGetStateUnsafe
title: KsGateGetStateUnsafe function
author: windows-driver-content
description: The KsGateGetStateUnsafe function returns the state of the given gate (open or closed) in an unsafe manner, that is without regard to synchronization.
old-location: stream\ksgategetstateunsafe.htm
old-project: stream
ms.assetid: f5976125-4ff4-48c2-a5c7-8e9fb2f8a0c9
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: avfunc_1f18b601-daaf-4df2-98c2-a91646f84c0d.xml, stream.ksgategetstateunsafe, ks/KsGateGetStateUnsafe, KsGateGetStateUnsafe, KsGateGetStateUnsafe function [Streaming Media Devices]
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KsGateGetStateUnsafe
product: Windows
targetos: Windows
req.typenames: 
---

# KsGateGetStateUnsafe function


## -description


The<b> KsGateGetStateUnsafe</b> function returns the state of the given gate (open or closed)  in an unsafe manner, that is <i>without regard to synchronization</i>.


## -syntax


````
BOOLEAN __inline KsGateGetStateUnsafe(
  _In_ PKSGATE Gate
);
````


## -parameters




### -param Gate [in]

A pointer to a <a href="..\ks\ns-ks-_ksgate.md">KSGATE</a> structure representing the gate for which to return the state.


## -returns



This call returns <b>TRUE</b> if the gate is open and <b>FALSE</b> if the gate is closed.




## -remarks



Because <b>KsGateGetStateUnsafe</b> does not handle synchronization, it is possible to get a result that is not consistent with the state of the gate if the gate is in mid-transition from one state to another at the time of the call.

Consider a situation in which the output of gate A is connected as an input to gate B. A transitions to closed, causing B to transition from open to closed. If, at the same time, another thread calls <b>KsGateGetStateUnsafe</b> between the time A closes and the time B closes, the routine still returns that B was open.

<b>KsGateGetStateUnsafe</b> returns whether <i>Gate-&gt;Count</i> is greater than zero. The function does not use any interlocked functions to do this. Thus, the call is performed without regard to synchronization.



