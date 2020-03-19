---
UID: NS:ntifs._REPARSE_DATA_BUFFER_EX
title: _REPARSE_DATA_BUFFER_EX (ntifs.h)
description: The REPARSE_DATA_BUFFER_EX structure contains reparse point data for a reparse point.
ms.assetid: fcbcb8e5-293f-4a19-8015-99cd870669bf
ms.date: 05/31/2019
keywords: ["_REPARSE_DATA_BUFFER_EX structure"]
f1_keywords:
 - "ntifs/_REPARSE_DATA_BUFFER_EX"
ms.keywords: _REPARSE_DATA_BUFFER_EX, REPARSE_DATA_BUFFER_EX, *PREPARSE_DATA_BUFFER_EX, REPARSE_DATA_BUFFER
req.header: ntifs.h
req.include-header:
req.target-type:
req.target- min-winverclnt: Windows 10 (Version 1803)
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: REPARSE_DATA_BUFFER_EX, *PREPARSE_DATA_BUFFER_EX
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ntifs.h
api_name: 
- _REPARSE_DATA_BUFFER_EX
product:
- Windows
targetos: Windows
---

# _REPARSE_DATA_BUFFER_EX structure

## -description

The REPARSE_DATA_BUFFER_EX structure contains reparse point data for a reparse point.

## -struct-fields

### -field Flags

Can be the following value:

| Flag Value | Meaning |
| ---------- | ------- |
| REPARSE_DATA_EX_FLAG_GIVEN_TAG_OR_NONE | Forces [FSCTL_SET_REPARSE_POINT_EX](https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-set-reparse-point_ex) to set the reparse tag if the file has no tag, or if the tag on the file is same as the one in *ExistingReparseTag*. NOTE: If *ExistingReparseTag* is not a Microsoft tag, then *ExistingReparseGuid* should match if the file already has the *ExistingReparseTag.* |

### -field ExistingReparseTag

Reparse point tag on the file, if any, if the caller wants to also replace the reparse tag.

* To set the reparse data along with a reparse tag that might be different, *ExistingReparseTag* should be the current reparse tag of the file.
* To update the reparse data while maintaining the same reparse tag, *ExistingReparseTag* should be the existing reparse tag.
* To set the reparse tag along with reparse data on a file that does not yet have a reparse tag, *ExistingReparseTag* should be set to zero.

### -field ExistingReparseGuid

For non-Microsoft reparse tags, this is the existing reparse GUID on the file, if any, when the caller wants to replace the reparse tag and/or GUID along with the data. If *ExistingReparseTag* is zero, the file is not expected to have any reparse tags, so *ExistingReparseGuid* is ignored. For non-Microsoft tags, *ExistingReparseGuid* should match the GUID in the file if *ExistingReparseTag* is non-zero.

### -field Reserved

Reserved. Do not use.

### -field DUMMYUNIONNAME

### -field DUMMYUNIONNAME.ReparseDataBuffer

A [REPARSE_DATA_BUFFER](ns-ntifs-_reparse_data_buffer.md) structure that contains data for a Microsoft-defined reparse point.

### -field DUMMYUNIONNAME.ReparseGuidDataBuffer

A [REPARSE_GUID_DATA_BUFFER](ns-ntifs-_reparse_guid_data_buffer.md) structure that contains data for a reparse point. Third party reparse points must use this structure.

## -remarks

The REPARSE_DATA_BUFFER_EX structure is used to store data for a reparse point. Use REPARSE_DATA_BUFFER_EX when setting a reparse point on a file or directory through the [FSCTL_SET_REPARSE_POINT_EX](https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-set-reparse-point_ex) IOCTL.

## -see-also

[FSCTL_SET_REPARSE_POINT_EX](https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-set-reparse-point_ex)

[REPARSE_DATA_BUFFER](ns-ntifs-_reparse_data_buffer.md)

[REPARSE_GUID_DATA_BUFFER](ns-ntifs-_reparse_guid_data_buffer.md)
