---
UID: NE:storport._STORPORT_LIVEDUMP_ISSUE_TYPE
tech.root: storage
title: STORPORT_LIVEDUMP_ISSUE_TYPE
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
 - _STORPORT_LIVEDUMP_ISSUE_TYPE
 - PSTORPORT_LIVEDUMP_ISSUE_TYPE
 - STORPORT_LIVEDUMP_ISSUE_TYPE
f1_keywords:
 - _STORPORT_LIVEDUMP_ISSUE_TYPE
 - storport/_STORPORT_LIVEDUMP_ISSUE_TYPE
 - PSTORPORT_LIVEDUMP_ISSUE_TYPE
 - storport/PSTORPORT_LIVEDUMP_ISSUE_TYPE
 - STORPORT_LIVEDUMP_ISSUE_TYPE
 - storport/STORPORT_LIVEDUMP_ISSUE_TYPE
dev_langs:
 - c++
---

## -description

**STORPORT_LIVEDUMP_ISSUE_TYPE** identifies the issue that triggered the live dump capture.

## -enum-fields

### -field StorportLivedumpIssueTypeUndefined

The reason for the live dump trigger is not defined.

### -field StorportLivedumpIssueTypeDevicePanic

The hardware device has panicked.

## -remarks

**STORPORT_LIVEDUMP_ISSUE_TYPE** is a member of the[**STORPORT_CAPTURE_LIVEDUMP**](ns-storport-storport_capture_livedump.md) structure, which a miniport passes when it calls [**StorPortCaptureLiveDump**](nf-storport-storportcapturelivedump.md).

## -see-also

[**STORPORT_CAPTURE_LIVEDUMP**](ns-storport-storport_capture_livedump.md)

[**StorPortCaptureLiveDump**](nf-storport-storportcapturelivedump.md)
