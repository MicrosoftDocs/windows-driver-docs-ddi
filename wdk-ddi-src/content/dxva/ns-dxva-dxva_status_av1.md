---
UID: NS:dxva._DXVA_Status_AV1
tech.root: display
title: DXVA_Status_AV1
ms.date: 05/13/2021
targetos: Windows
description: The DXVA_Status_AV1 data structure is sent by the accelerator to the host software decoder to convey decoding status information.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dxva.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: DXVA_Status_AV1, *LPDXVA_Status_AV1
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dxva.h
api_name:
 - _DXVA_Status_AV1
 - LPDXVA_Status_AV1
 - DXVA_Status_AV1
f1_keywords:
 - _DXVA_Status_AV1
 - dxva/_DXVA_Status_AV1
 - LPDXVA_Status_AV1
 - dxva/LPDXVA_Status_AV1
 - DXVA_Status_AV1
 - dxva/DXVA_Status_AV1
dev_langs:
 - c++
---

## -description

The **DXVA_Status_AV1** structure is sent by the accelerator to the host software decoder to convey decoding status information.

## -struct-fields

### -field StatusReportFeedbackNumber

Contains the value of **StatusReportFeedbackNumber** set by the host software decoder in the [**DXVA_PicParams_AV1**](ns-dxva-dxva_picparams_av1.md) structure for the associated operation.

### -field CurrPic

The uncompressed destination surface that was affected by the operation.

### -field BufType

The type of compressed buffer associated with this status report. If **Status** is 0, **bBufType** may be 0xFF, which indicates that the status report applies to all of the compressed buffers conveyed in the associated Execute call. Otherwise, if **bBufType** is not 0xFF, it must contain one of the following values, defined in *dxva.h*:

| Value | Description |
| ----- | ----------- |
| DXVA_PICTURE_DECODE_BUFFER (1) | Picture decoding parameter buffer. |
| DXVA_SLICE_CONTROL_BUFFER (6)  | Slice control buffer.              |
| DXVA_BITSTREAM_DATA_BUFFER (7) | Bitstream data buffer.             |

### -field Status

The status of the operation. **Status** can be one of the following values:

| Value | Description |
| ----- | ----------- |
| 0     | The operation succeeded. |
| 1     | Minor problem in the data format. The host decoder should continue processing. |
| 2     | Significant problem in the data format. The host decoder may continue executing or skip the display of the output picture. |
| 3     | Severe problem in the data format. The host decoder should restart the entire decoding process, starting at a sequence or random-access entry point. |
| 4     | Other severe problem. The host decoder should restart the entire decoding process, starting at a sequence or random-access entry point. |

If the value is 3 or 4, the host software decoder should halt the decoding process unless it can take corrective action.

### -field Reserved8Bits

Reserved; set to 0. The accelerator ignores this field.

### -field NumMbsAffected

If **Status** is not 0, this member contains the accelerator's estimate of the number of super-blocks in the decoded frame that were adversely affected by the reported problem. If the accelerator does not provide an estimate, the value is 0xFFFF.

If **Status** is 0, the accelerator may set **NumMbsAffected** to the number of super-blocks that were successfully decoded by the operation. If the accelerator does not provide an estimate, it shall set the value either to 0 or to 0xFFFF.

## -remarks

See the [Direct X Video Acceleration Specification for AV1 Video Coding](https://www.microsoft.com/download/details.aspx?id=101577) for detailed information, including how to use this structure.
