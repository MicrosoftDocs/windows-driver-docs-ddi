---
UID: NS:ks._KSGATE
title: _KSGATE
author: windows-driver-content
description: The KSGATE structure describes an AVStream gate object.
old-location: stream\ksgate.htm
old-project: stream
ms.assetid: f6b5169e-2ff1-43da-a207-0c15c75e1367
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _KSGATE, *PKSGATE, KSGATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSGATE
req.alt-loc: ks.h
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
req.typenames: *PKSGATE, KSGATE
---

# _KSGATE structure



## -description
The KSGATE structure describes an AVStream gate object.



## -syntax

````
typedef struct _KSGATE {
  LONG    Count;
  PKSGATE NextGate;
} KSGATE, *PKSGATE;
````


## -struct-fields

### -field Count

This member indicates the count on the gate. When this member is above zero, the gate is considered to be in the "open" state and allows processing. When the member is zero or below, the gate is considered to be in the "closed" state and does not allow processing. Although the KSGATE structure is the universal gate implementation in AVStream, conceptually, there are both AND and OR gates. For AND gates, Count is one minus the number of off inputs to the gate. For OR gates, Count is the number of on inputs for the gate. Thus, in general, this member can contain any value; however, for AND gates, it can only contain values of one or less, and for OR gates, it can only contain values of zero or greater. Clients should be careful not to specifically set the Count member to an invalid value for the given conceptual gate this structure represents. 



### -field NextGate

A pointer to the next KSGATE structure in the gate chain. There are restrictions on this propagation using the KsGateXxxAnd and KsGateXxxOr functions. NextGate for an AND gate must point to an OR gate, and for an OR gate must point to an AND gate. Clients can specify state transitions manually via KsGateInitialize instead of KsGateInitializeAnd or KsGateInitializeOr.


## -remarks
Conceptually, flow control gates are logical AND and OR gates; in AVStream, they are used as a processing-control mechanism. For more information, see <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.

All of the manipulations of <b>Count</b> are done using interlocked functions to provide synchronous state changes. There is no distinction as to whether a given KSGATE represents an AND gate or an OR gate. Thus, clients should be careful not to transition a gate into an invalid state by using <b>KSGATE</b><i>Xxx</i><b>And</b> functions on an OR gate or <b>KSGATE</b><i>Xxx</i><b>Or</b> functions on an AND gate or by using <b>KsGateTurnInput</b><i>Xxx</i> functions invalidly.


## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ksgateinitialize.md">KsGateInitialize</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgateinitializeand.md">KsGateInitializeAnd</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgateinitializeor.md">KsGateInitializeOr</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_ksgate.md">KSGATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSGATE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

