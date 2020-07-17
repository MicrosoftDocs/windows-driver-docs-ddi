---
UID: NF:ks.KsPinSubmitFrame
title: KsPinSubmitFrame function (ks.h)
description: If a pin has been placed into injection mode by a call to KsPinRegisterFrameReturnCallback, the KsPinSubmitFrame function submits a frame directly into the transport circuit.
old-location: stream\kspinsubmitframe.htm
tech.root: stream
ms.assetid: 3fdb83b2-85b7-4f86-9a59-a42138000214
ms.date: 04/23/2018
keywords: ["KsPinSubmitFrame function"]
ms.keywords: KsPinSubmitFrame, KsPinSubmitFrame function [Streaming Media Devices], avfunc_ce7c4c71-c404-4061-a2e5-b9f4c15df4a2.xml, ks/KsPinSubmitFrame, stream.kspinsubmitframe
f1_keywords:
 - "ks/KsPinSubmitFrame"
 - "KsPinSubmitFrame"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsPinSubmitFrame
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinSubmitFrame function


## -description


If a pin has been placed into injection mode by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspinregisterframereturncallback">KsPinRegisterFrameReturnCallback</a>, the <b>KsPinSubmitFrame</b> function submits a frame directly into the transport circuit.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure on which to submit a frame.


### -param Data [in, optional]

A pointer to a frame buffer. This should be <b>NULL</b> if and only if <i>Size</i> is equal to 0. Optional.


### -param OPTIONAL




### -param StreamHeader [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksstream_header">KSSTREAM_HEADER</a> structure. The stream header is copied if this parameter is supplied. Optional.


### -param Context [in, optional]

A pointer to a caller-allocated buffer. AVStream provides this pointer to the frame return callback registered through a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspinregisterframereturncallback">KsPinRegisterFrameReturnCallback</a>. Optional.


#### - Size [in, optional]

The size in bytes of the frame buffer to which the <i>Data</i> field points. If the <i>Data</i> field is <b>NULL</b>, set this parameter to zero. Optional.


## -returns



Returns STATUS_SUCCESS if frame submission is successful. Otherwise returns an appropriate error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspinregisterframereturncallback">KsPinRegisterFrameReturnCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspinsubmitframemdl">KsPinSubmitFrameMdl</a>
 

 

