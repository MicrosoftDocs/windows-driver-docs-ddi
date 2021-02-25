---
UID: NS:storport._STORPORT_LIVEDUMP_DEVICE_TELEMETRY_LOG
tech.root: storage
title: STORPORT_LIVEDUMP_DEVICE_TELEMETRY_LOG
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: 
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
req.target-type: 
req.typenames: STORPORT_LIVEDUMP_DEVICE_TELEMETRY_LOG, *PSTORPORT_LIVEDUMP_DEVICE_TELEMETRY_LOG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STORPORT_LIVEDUMP_DEVICE_TELEMETRY_LOG
 - PSTORPORT_LIVEDUMP_DEVICE_TELEMETRY_LOG
 - STORPORT_LIVEDUMP_DEVICE_TELEMETRY_LOG
f1_keywords:
 - _STORPORT_LIVEDUMP_DEVICE_TELEMETRY_LOG
 - storport/_STORPORT_LIVEDUMP_DEVICE_TELEMETRY_LOG
 - PSTORPORT_LIVEDUMP_DEVICE_TELEMETRY_LOG
 - storport/PSTORPORT_LIVEDUMP_DEVICE_TELEMETRY_LOG
 - STORPORT_LIVEDUMP_DEVICE_TELEMETRY_LOG
 - storport/STORPORT_LIVEDUMP_DEVICE_TELEMETRY_LOG
dev_langs:
 - c++
---

## -description

## -struct-fields

### -field Version

Size, in bytes, of this structure. The structure size serves as the version.

### -field Size

Size, in bytes, of this structure plus all of its variable-sized fields.

### -field BucketId

Unique identifier for the device's state when the issue occurs.

### -field OrganizationID

The IEEE organizationally unique identifier (OUI).

### -field Reserved

Reserved; do not use.

### -field TelemetryLength

Size, in bytes, of the telemetry log that **DeviceTelemetry** points to.

### -field DeviceTelemetry

Pointer to the device-defined telemetry log.

## -remarks

When a miniport calls [**StorPortCaptureLiveDump**](nf-storport-storportcapturelivedump.md) with [**STORPORT_CAPTURE_LIVEDUMP**](ns-storport-storport_capture_livedump.md).**DataType** set to **StorportLivedumpDataTypeDeviceTelemetryLog**,  **STORPORT_CAPTURE_LIVEDUMP.Data** points to a **STORPORT_LIVEDUMP_DEVICE_TELEMETRY_LOG** structure that contains the payload for the live dump.

## -see-also

[**STORPORT_LIVEDUMP_DATA_TYPE**](ne-storport-storport_livedump_data_type.md)

[**StorPortCaptureLiveDump**](nf-storport-storportcapturelivedump.md)
