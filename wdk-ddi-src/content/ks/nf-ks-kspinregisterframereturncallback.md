---
UID: NF:ks.KsPinRegisterFrameReturnCallback
title: KsPinRegisterFrameReturnCallback function (ks.h)
description: The KsPinRegisterFrameReturnCallback function registers a frame return callback with AVStream for a given pin.
old-location: stream\kspinregisterframereturncallback.htm
tech.root: stream
ms.assetid: 480f33e7-6fe6-40a1-9e1b-351378b7e003
ms.date: 04/23/2018
ms.keywords: KsPinRegisterFrameReturnCallback, KsPinRegisterFrameReturnCallback function [Streaming Media Devices], avfunc_16d1d4cd-f3ae-4cc0-b903-1db1f5b40a6f.xml, ks/KsPinRegisterFrameReturnCallback, stream.kspinregisterframereturncallback
ms.topic: function
f1_keywords:
 - "ks/KsPinRegisterFrameReturnCallback"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsPinRegisterFrameReturnCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinRegisterFrameReturnCallback function


## -description


The<b> KsPinRegisterFrameReturnCallback </b>function registers a frame return callback with AVStream for a given pin.


## -parameters




### -param Pin [in]

A pointer to the AVStream <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_kspin">KSPIN</a> structure that you want to place into injection mode by registering a frame return callback.


### -param FrameReturn [in]

This parameter supplies the address of a minidriver-provided <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnkspinframereturn">AVStrMiniFrameReturn</a> routine.


## -returns



None




## -remarks



If a pin has registered a frame return callback before transitioning from <b>KSSTATE_STOP</b> to KSSTATE_ACQUIRE, the pin is placed into injection mode. This indicates that the pin will not receive buffers and fill them, but rather manually inject data frames into the circuit using <b>KsPinSubmitFrame </b>or <b>KsPinSubmitFrameMdl</b>. When the data frame completes its travel around the circuit and returns to the pin on which it was submitted, AVStream recycles it by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnkspinframereturn">AVStrMiniFrameReturn</a>.

Minidrivers that call this function are directly responsible for injecting frames into the circuit; they do not receive buffers to fill and do not directly interact with the queue as do most minidrivers. Also note that the frame return callback should be registered before the kernel pipe section is created. The kernel pipe section is created when the pin transitions to KSSTATE_ACQUIRE. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/frame-injection">Frame Injection</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnkspinframereturn">AVStrMiniFrameReturn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspinsubmitframe">KsPinSubmitFrame</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspinsubmitframemdl">KsPinSubmitFrameMdl</a>
 

 

