---
UID: NS:d3dumddi._D3DDDI_BATCHEDMARKERDATA
title: D3DDDI_BATCHEDMARKERDATA
ms.date: 03/24/2020
ms.topic: language-reference
targetos: Windows
tech.root: display
description: The D3DDDI_BATCHEDMARKERDATA structure provides high-performance marker data from D3D12 drivers.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dumddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DDDI_BATCHEDMARKERDATA
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDI_BATCHEDMARKERDATA
 - D3DDDI_BATCHEDMARKERDATA
f1_keywords:
 - _D3DDDI_BATCHEDMARKERDATA
 - d3dumddi/_D3DDDI_BATCHEDMARKERDATA
 - D3DDDI_BATCHEDMARKERDATA
 - d3dumddi/D3DDDI_BATCHEDMARKERDATA
dev_langs:
 - c++
---

## -description

The **D3DDDI_BATCHEDMARKERDATA** structure provides high-performance marker data from D3D12 drivers.

## -struct-fields

### -field hRTCommandListHandle

D3D12DDI_HRTCOMMANDLIST::handle value for the command list that this marker data corresponds to. This handle was provided during command list creation.

### -field FirstAPISequenceNumberHigh

The high bits of the API sequence numbers represented by this batch of marker data.

### -field CompletedAPISequenceNumberLowSize

The number of API sequence numbers present in this batch of marker data (the number of elements in **pCompletedAPISequenceNumberLow**).

### -field pCompletedAPISequenceNumberLow

Array of the low bits of API sequence numbers represented by this batch of marker data.

## -remarks

The driver is responsible for filling out this structure when submitting rendering work or history buffers to the runtime, and when the driver uses the D3DDDIMLT_BATCHED value for the **MarkerLogType** field in the structure that contains this structure. The containing structure could be one of [**D3DDDICB_RENDER**](ns-d3dumddi-_d3dddicb_render.md), [**D3DDDICB_SUBMITCOMMAND**](ns-d3dumddi-_d3dddicb_submitcommand.md), or [**D3DDDICB_SUBMITHISTORYSEQUENCE**](ns-d3dumddi-d3dddicb_submithistorysequence.md). See [**D3DDDI_MARKERLOGTYPE**](ne-d3dumddi-d3dddi_markerlogtype.md) for details on when a driver should set D3DDDIMLT_BATCHED.

## -see-also

[**D3DDDI_MARKERLOGTYPE**](ne-d3dumddi-d3dddi_markerlogtype.md)

[**D3DDDICB_RENDER**](ns-d3dumddi-_d3dddicb_render.md)

[**D3DDDICB_SUBMITCOMMAND**](ns-d3dumddi-_d3dddicb_submitcommand.md)

[**D3DDDICB_SUBMITHISTORYSEQUENCE**](ns-d3dumddi-d3dddicb_submithistorysequence.md)
