---
UID: NS:storport._STORPORT_CAPTURE_LIVEDUMP
tech.root: storage
title: STORPORT_CAPTURE_LIVEDUMP
ms.date: 05/13/2021
targetos: Windows
description: The STORPORT_CAPTURE_LIVEDUMP structure contains the data needed to generate a live dump.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: STORPORT_CAPTURE_LIVEDUMP, *PSTORPORT_CAPTURE_LIVEDUMP
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STORPORT_CAPTURE_LIVEDUMP
 - PSTORPORT_CAPTURE_LIVEDUMP
 - STORPORT_CAPTURE_LIVEDUMP
f1_keywords:
 - _STORPORT_CAPTURE_LIVEDUMP
 - storport/_STORPORT_CAPTURE_LIVEDUMP
 - PSTORPORT_CAPTURE_LIVEDUMP
 - storport/PSTORPORT_CAPTURE_LIVEDUMP
 - STORPORT_CAPTURE_LIVEDUMP
 - storport/STORPORT_CAPTURE_LIVEDUMP
dev_langs:
 - c++
---

## -description

The **STORPORT_CAPTURE_LIVEDUMP** structure contains the data needed to generate a live dump.

## -struct-fields

### -field Version

Size, in bytes, of this structure. The structure size serves as the version.

### -field Size

Size, in bytes, of this structure plus all of its variable-sized fields.

### -field LiveDumpType

A [**STORPORT_CAPTURE_LIVEDUMP_TYPE**](ne-storport-storport_capture_livedump_type.md) enum value that identifies the type of live dump to capture.

### -field IssueType

A [**STORPORT_LIVEDUMP_ISSUE_TYPE**](ne-storport-storport_livedump_issue_type.md) enum value that identifies the issue that triggers the live dump capture.

### -field ComponentName

Pointer to a string name that identifies the component that is creating the live dump.

### -field DataType

A [**STORPORT_LIVEDUMP_DATA_TYPE**](ne-storport-storport_livedump_data_type.md) enum value that specifies the data type of the payload to be included in the live dump.

### -field Data

Pointer to the payload to be included in the live dump.

## -remarks

A miniport calls [**StorPortCaptureLiveDump**](nf-storport-storportcapturelivedump.md) with the data in this structure to capture a live dump file.

## -see-also

[**STORPORT_CAPTURE_LIVEDUMP_TYPE**](ne-storport-storport_capture_livedump_type.md)

[**STORPORT_LIVEDUMP_DATA_TYPE**](ne-storport-storport_livedump_data_type.md)

[**STORPORT_LIVEDUMP_ISSUE_TYPE**](ne-storport-storport_livedump_issue_type.md)

[**StorPortCaptureLiveDump**](nf-storport-storportcapturelivedump.md)
