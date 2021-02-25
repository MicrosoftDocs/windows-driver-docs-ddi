---
UID: NE:storport._STORPORT_CAPTURE_LIVEDUMP_TYPE
tech.root: storage
title: STORPORT_CAPTURE_LIVEDUMP_TYPE
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: 
req.construct-type: enumeration
req.ddi-compliance: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STORPORT_CAPTURE_LIVEDUMP_TYPE
 - PSTORPORT_CAPTURE_LIVEDUMP_TYPE
 - STORPORT_CAPTURE_LIVEDUMP_TYPE
f1_keywords:
 - _STORPORT_CAPTURE_LIVEDUMP_TYPE
 - storport/_STORPORT_CAPTURE_LIVEDUMP_TYPE
 - PSTORPORT_CAPTURE_LIVEDUMP_TYPE
 - storport/PSTORPORT_CAPTURE_LIVEDUMP_TYPE
 - STORPORT_CAPTURE_LIVEDUMP_TYPE
 - storport/STORPORT_CAPTURE_LIVEDUMP_TYPE
dev_langs:
 - c++
---

## -description

**STORPORT_CAPTURE_LIVEDUMP_TYPE** identifies the type of live dump to capture.

## -enum-fields

### -field StorportCaptureLiveDumpTypeUndefined

### -field StorportCaptureLiveDumpTypeMini

Capture a mini dump with the smallest set of useful information about the issue.

### -field StorportCaptureLiveDumpTypeFull

Capture a full kernel dump.

## -remarks

**STORPORT_CAPTURE_LIVEDUMP_TYPE** is a member of the[**STORPORT_CAPTURE_LIVEDUMP**](ns-storport-storport_capture_livedump.md) structure, which a miniport passes when it calls [**StorPortCaptureLiveDump**](nf-storport-storportcapturelivedump.md).

## -see-also

[**STORPORT_CAPTURE_LIVEDUMP**](ns-storport-storport_capture_livedump.md)

[**StorPortCaptureLiveDump**](nf-storport-storportcapturelivedump.md)
