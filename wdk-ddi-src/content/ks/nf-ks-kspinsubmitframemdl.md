---
UID: NF:ks.KsPinSubmitFrameMdl
title: KsPinSubmitFrameMdl function (ks.h)
description: If a pin has been placed into injection mode by a call to KsPinRegisterFrameReturnCallback, the KsPinSubmitFrameMdl function submits a frame directly into the transport circuit.
old-location: stream\kspinsubmitframemdl.htm
tech.root: stream
ms.assetid: 8033c0a9-86dd-4d54-b93e-66c926cae952
ms.date: 04/23/2018
keywords: ["KsPinSubmitFrameMdl function"]
ms.keywords: KsPinSubmitFrameMdl, KsPinSubmitFrameMdl function [Streaming Media Devices], avfunc_456aa5db-b749-4b95-8448-f024dbc2030b.xml, ks/KsPinSubmitFrameMdl, stream.kspinsubmitframemdl
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KsPinSubmitFrameMdl
 - ks/KsPinSubmitFrameMdl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsPinSubmitFrameMdl
---

# KsPinSubmitFrameMdl function


## -description

If a pin has been placed into injection mode by a call to <a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinregisterframereturncallback">KsPinRegisterFrameReturnCallback</a>, the <b>KsPinSubmitFrameMdl</b> function submits a frame directly into the transport circuit.

## -parameters

### -param Pin 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure representing the pin on which to submit a frame.

### -param Mdl 

[in, optional]
A pointer to a memory descriptor list describing the frame buffer. Optional.

### -param StreamHeader 

[in, optional]
A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksstream_header">KSSTREAM_HEADER</a> structure. The stream header is copied if this parameter is supplied. Optional.

### -param Context 

[in, optional]
A pointer to a caller-allocated buffer that is passed to the frame return callback registered through <a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinregisterframereturncallback">KsPinRegisterFrameReturnCallback</a>. This parameter is optional and is solely for the caller's use.

## -returns

Returns STATUS_SUCCESS if frame submission is successful. Otherwise returns an appropriate error code.

## -remarks

The difference between this function and <a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinsubmitframe">KsPinSubmitFrame</a> is that this function will submit a frame using an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a> structure rather than a data and size argument.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinregisterframereturncallback">KsPinRegisterFrameReturnCallback</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspinsubmitframe">KsPinSubmitFrame</a>