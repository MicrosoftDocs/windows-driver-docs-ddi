---
UID: NF:ks.KsGateInitialize
title: KsGateInitialize function
author: windows-driver-content
description: The KsGateInitialize function initializes a gate for use.
old-location: stream\ksgateinitialize.htm
old-project: stream
ms.assetid: e64715d2-a8f1-47c3-9422-b565800ff79e
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsGateInitialize, KsGateInitialize function [Streaming Media Devices], avfunc_1ec7041b-e335-4920-ad40-06290d1579c2.xml, ks/KsGateInitialize, stream.ksgateinitialize
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KsGateInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGateInitialize function


## -description


The<b> KsGateInitialize</b> function initializes a gate for use.


## -parameters




### -param Gate [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a> structure to initialize.


### -param InitialCount [in]

This parameter specifies the initial count to place on the gate. Fills in <i>Gate -&gt; Count</i>. For a new AND gate, this should be 1 (1 − 0 off inputs), and for a new OR gate, this should be 0 (0 on inputs). For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.


### -param NextGate [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a> structure to which <i>Gate</i> should attach its output for state transitions. If this optional parameter is unspecified, <i>Gate</i> is not be attached to a subsequent gate.


### -param StateToPropagate [in]

This parameter specifies whether to propagate ON transitions or OFF transitions. For an OR gate, set to <b>TRUE</b>; for an AND gate, set to <b>FALSE</b>.


## -returns



None




## -remarks



Minidrivers should not call <b>KsGateInitialize</b> directly, but should instead use <a href="https://msdn.microsoft.com/library/windows/hardware/ff562574">KsGateInitializeAnd</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff562576">KsGateInitializeOr</a>.

AND and OR gates are conceptualizations of the gating mechanism. AVStream does not distinguish between them in the implementation of the common gate functions. The gate functions specific to AND and OR gates are inline calls to the common gate functions.

To learn more about the gate construct in AVStream, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562574">KsGateInitializeAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562576">KsGateInitializeOr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562586">KsGateTerminateAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562588">KsGateTerminateOr</a>
 

 

