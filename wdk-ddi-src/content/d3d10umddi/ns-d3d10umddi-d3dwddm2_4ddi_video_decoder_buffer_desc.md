---
UID: NS:d3d10umddi.D3DWDDM2_4DDI_VIDEO_DECODER_BUFFER_DESC
title: D3DWDDM2_4DDI_VIDEO_DECODER_BUFFER_DESC (d3d10umddi.h)
description: Represents additional decode parameters.
ms.assetid: 24258007-5a94-4292-92d7-36e280c73fc8
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3d10umddi/D3DWDDM2_4DDI_VIDEO_DECODER_BUFFER_DESC"
ms.keywords: D3DWDDM2_4DDI_VIDEO_DECODER_BUFFER_DESC, D3DWDDM2_4DDI_VIDEO_DECODER_BUFFER_DESC,
req.header: d3d10umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DWDDM2_4DDI_VIDEO_DECODER_BUFFER_DESC
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3DWDDM2_4DDI_VIDEO_DECODER_BUFFER_DESC
product: 
- Windows
targetos: Windows
tech.root: display
---

# D3DWDDM2_4DDI_VIDEO_DECODER_BUFFER_DESC structure

## -description

Represents additional decode parameters.

## -struct-fields

### -field hResource

The source decoder buffer.

### -field BufferType

The type of buffer.

### -field DataOffset

The offset of the relevant data from the beginning of the buffer, in bytes. This value must be zero.

### -field DataSize

Size of the relevant data.

### -field pIV

A pointer to a buffer that contains an initialization vector (IV) for encrypted data. If the decode buffer does not contain encrypted data, set this member to NULL.

### -field IVSize

The size of the buffer specified in the pIV parameter. If pIV is NULL, set this member to zero.

### -field pSubSampleMappingBlock

A pointer to an array of D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK structures, which indicates exactly which bytes in the decode buffer are encrypted and which are in the clear. If the decode buffer does not contain encrypted data, set this member to NULL.

>**Note**  Values in the sub sample mapping blocks are relative to the start of the decode buffer.


### -field SubSampleMappingCount

The number of D3DWDDM2_0DDI_VIDEO_DECODER_SUB_SAMPLE_MAPPING_BLOCK structures specified in the pSubSampleMappingBlocks parameter. If pSubSampleMappingBlocks is NULL, set this member to zero.

### -field cBlocksStripeEncrypted

Indicates the number of 16-byte BLOCKS that are encrypted in any given encrypted region mapping, as defined by the CENS and CBCS schemes in the common encryption spec.

If this value is zero:

* All bytes each encrypted region mapping are encrypted, i.e. the CENC or CBC1 scheme is being used.
* cBlocksStripeClear must also be zero.

If this value is non-zero, cBlocksStripeClear must also be non-zero.

>**Note**  This value will typically be ZERO or ONE in real-world content, but the spec merely recommends this and does not require it

### -field cBlocksStripeClear

Indicates the number of 16-byte BLOCKS that are clear in any given encrypted region mapping, as defined by the CENS and CBCS schemes in the common encryption spec.

If this value is zero, all bytes each encrypted region mapping are encrypted, i.e. the CENC or CBC1 scheme is being used.

## -remarks

## -see-also
