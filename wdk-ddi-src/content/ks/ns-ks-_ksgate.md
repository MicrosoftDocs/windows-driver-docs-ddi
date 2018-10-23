---
UID: NS:ks._KSGATE
title: "_KSGATE"
author: windows-driver-content
description: The KSGATE structure describes an AVStream gate object.
old-location: stream\ksgate.htm
tech.root: stream
ms.assetid: f6b5169e-2ff1-43da-a207-0c15c75e1367
ms.date: 04/23/2018
ms.keywords: "*PKSGATE, KSGATE, KSGATE structure [Streaming Media Devices], PKSGATE, PKSGATE structure pointer [Streaming Media Devices], _KSGATE, avstruct_b232aae6-2b0a-44f9-beaf-29fe4b7f8b86.xml, ks/KSGATE, ks/PKSGATE, stream.ksgate"
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
-	KSGATE
product:
- Windows
targetos: Windows
req.typenames: KSGATE, *PKSGATE
---

# _KSGATE structure


## -description


The KSGATE structure describes an AVStream gate object.


## -struct-fields




### -field Count

This member indicates the count on the gate. When this member is above zero, the gate is considered to be in the "open" state and allows processing. When the member is zero or below, the gate is considered to be in the "closed" state and does not allow processing. Although the KSGATE structure is the universal gate implementation in AVStream, conceptually, there are both AND and OR gates. For AND gates, Count is one minus the number of off inputs to the gate. For OR gates, Count is the number of on inputs for the gate. Thus, in general, this member can contain any value; however, for AND gates, it can only contain values of one or less, and for OR gates, it can only contain values of zero or greater. Clients should be careful not to specifically set the Count member to an invalid value for the given conceptual gate this structure represents. 



### -field NextGate

A pointer to the next KSGATE structure in the gate chain. There are restrictions on this propagation using the KsGateXxxAnd and KsGateXxxOr functions. NextGate for an AND gate must point to an OR gate, and for an OR gate must point to an AND gate. Clients can specify state transitions manually via KsGateInitialize instead of KsGateInitializeAnd or KsGateInitializeOr.


## -remarks



Conceptually, flow control gates are logical AND and OR gates; in AVStream, they are used as a processing-control mechanism. For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.

All of the manipulations of <b>Count</b> are done using interlocked functions to provide synchronous state changes. There is no distinction as to whether a given KSGATE represents an AND gate or an OR gate. Thus, clients should be careful not to transition a gate into an invalid state by using <b>KSGATE</b><i>Xxx</i><b>And</b> functions on an OR gate or <b>KSGATE</b><i>Xxx</i><b>Or</b> functions on an AND gate or by using <b>KsGateTurnInput</b><i>Xxx</i> functions invalidly.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562566">KSGATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562573">KsGateInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562574">KsGateInitializeAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562576">KsGateInitializeOr</a>
 

 

