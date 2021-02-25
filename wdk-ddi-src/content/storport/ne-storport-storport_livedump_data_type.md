---
UID: NE:storport._STORPORT_LIVEDUMP_DATA_TYPE
tech.root: storage
title: STORPORT_LIVEDUMP_DATA_TYPE
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
 - _STORPORT_LIVEDUMP_DATA_TYPE
 - PSTORPORT_LIVEDUMP_DATA_TYPE
 - STORPORT_LIVEDUMP_DATA_TYPE
f1_keywords:
 - _STORPORT_LIVEDUMP_DATA_TYPE
 - storport/_STORPORT_LIVEDUMP_DATA_TYPE
 - PSTORPORT_LIVEDUMP_DATA_TYPE
 - storport/PSTORPORT_LIVEDUMP_DATA_TYPE
 - STORPORT_LIVEDUMP_DATA_TYPE
 - storport/STORPORT_LIVEDUMP_DATA_TYPE
dev_langs:
 - c++
---

## -description

**STORPORT_LIVEDUMP_DATA_TYPE** identifies the data type of the payload to be included in the live dump.

## -enum-fields

### -field StorportLivedumpDataTypeUndefined

### -field StorportLivedumpDataTypeDeviceTelemetryLog

Include a payload of type [**STORPORT_LIVEDUMP_DEVICE_TELEMETRY_LOG**](ns-storport-storport_livedump_device_telemetry_log.md).

## -remarks

**STORPORT_LIVEDUMP_DATA_TYPE** identifies the payload structure pointed to by the **Data** member of the[**STORPORT_CAPTURE_LIVEDUMP**](ns-storport-storport_capture_livedump.md) structure, which a miniport passes when it calls [**StorPortCaptureLiveDump**](nf-storport-storportcapturelivedump.md).

## -see-also

[**STORPORT_CAPTURE_LIVEDUMP**](ns-storport-storport_capture_livedump.md)

[**STORPORT_LIVEDUMP_DEVICE_TELEMETRY_LOG**](ns-storport-storport_livedump_device_telemetry_log.md

[**StorPortCaptureLiveDump**](nf-storport-storportcapturelivedump.md)
