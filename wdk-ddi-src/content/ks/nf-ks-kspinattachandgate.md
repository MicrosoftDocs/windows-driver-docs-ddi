---
UID: NF:ks.KsPinAttachAndGate
title: KsPinAttachAndGate function (ks.h)
description: The KsPinAttachAndGate function connects Pin as an input to a previously initialized AND gate, and connects AndGate as an input to the relevant filter's AND gate.
old-location: stream\kspinattachandgate.htm
tech.root: stream
ms.assetid: 63081b07-add8-49fc-b12d-6aa5c43356ce
ms.date: 04/23/2018
keywords: ["KsPinAttachAndGate function"]
ms.keywords: KsPinAttachAndGate, KsPinAttachAndGate function [Streaming Media Devices], avfunc_395e0cf9-ba21-4b20-a37b-7758d1bfeca0.xml, ks/KsPinAttachAndGate, stream.kspinattachandgate
f1_keywords:
 - "ks/KsPinAttachAndGate"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL (See Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsPinAttachAndGate
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinAttachAndGate function


## -description


The<b> KsPinAttachAndGate</b> function connects <i>Pin</i> as an input to a previously initialized AND gate, and connects <i>AndGate</i> as an input to the relevant filter's AND gate.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure to use an input to the AND gate.


### -param AndGate [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a> structure that is the previously initialized AND gate to connect to the relevant filter's AND gate. If this optional parameter is <b>NULL</b>, any <b>KSGATE</b> currently attached to the pin is detached.


## -remarks



To insert the gate, first call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateinitializeand">KsGateInitializeAnd</a>. Then call <b>KsPinAttachAndGate</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/flow-control-gates-in-avstream">Flow Control Gates in AVStream</a>.

<b>KsPinAttachAndGate </b>must be called at IRQL = PASSIVE_LEVEL before the pin in question leaves KSSTATE_STOP.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksgate">KSGATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgateinitializeand">KsGateInitializeAnd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspinattachorgate">KsPinAttachOrGate</a>
 

 

