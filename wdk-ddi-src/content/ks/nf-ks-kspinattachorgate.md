---
UID: NF:ks.KsPinAttachOrGate
title: KsPinAttachOrGate function (ks.h)
description: The KsPinAttachOrGate function connects Pin as an input to a previously initialized OR gate, and connects OrGate as an input to the relevant filter's AND gate.
old-location: stream\kspinattachorgate.htm
tech.root: stream
ms.assetid: 14fb5b30-7169-4d8a-ad72-d0ee86da7f98
ms.date: 04/23/2018
ms.keywords: KsPinAttachOrGate, KsPinAttachOrGate function [Streaming Media Devices], avfunc_bcc291d4-ee61-4196-88df-b7aef567a06b.xml, ks/KsPinAttachOrGate, stream.kspinattachorgate
ms.topic: function
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
- KsPinAttachOrGate
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinAttachOrGate function


## -description


The<b> KsPinAttachOrGate</b> function connects <i>Pin</i> as an input to a previously initialized OR gate, and connects <i>OrGate</i> as an input to the relevant filter's AND gate. 


## -parameters




### -param Pin [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_kspin">KSPIN</a> structure to use an input to the OR gate.


### -param OrGate [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksgate">KSGATE</a> structure that is the previously initialized OR gate to connect to the relevant filter's AND gate. If this optional parameter is NULL, any <b>KSGATE</b> currently attached to the pin is detached.


## -returns



None




## -remarks



To insert the gate, first call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgateinitializeor">KsGateInitializeOr</a>. Then call <b>KsPinAttachOrGate</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/flow-control-gates-in-avstream">Flow Control Gates in AVStream</a>.

Do not leave an unattached OR gate at filter creation time. Instead, create the OR gate later, for example  when the minidriver instantiates the pin.

<b>KsPinAttachOrGate </b>must be called at IRQL = PASSIVE_LEVEL before the pin in question leaves KSSTATE_STOP.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksgate">KSGATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgateinitializeor">KsGateInitializeOr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspinattachandgate">KsPinAttachAndGate</a>
 

 

