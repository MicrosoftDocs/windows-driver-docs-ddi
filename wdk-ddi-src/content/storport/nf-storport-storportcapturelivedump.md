---
UID: NF:storport.StorPortCaptureLiveDump
tech.root: storage
title: StorPortCaptureLiveDump
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: StorPortCaptureLiveDump captures a live dump file.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortCaptureLiveDump
f1_keywords:
 - StorPortCaptureLiveDump
 - storport/StorPortCaptureLiveDump
dev_langs:
 - c++
---

## -description

**StorPortCaptureLiveDump** captures a live dump file.

## -parameters

### -param HwDeviceExtension

[in] Pointer to the miniport's hardware device extension.

### -param StorAddress

[in/optional] Pointer to a [**STOR_ADDRESS**](ns-storport-_stor_address.md) structure that holds the address specifying the unit object. Set **StorAddress** to NULL if the device is an adapter.

### -param CaptureLivedump

[in] Pointer to a [**STORPORT_CAPTURE_LIVEDUMP**](ns-storport-storport_capture_livedump.md) structure containing the data needed to generate the live dump.

## -returns

**StorPortCaptureLiveDump** returns one of the following values:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_SUCCESS | The dump feature list was set successfully. |
| STOR_STATUS_INVALID_PARAMETER | One or more of the provided parameters are invalid. |
| STOR_STATUS_UNSUCCESSFUL | Returned for other internal system reasons. |

## -remarks

When a miniport detects an issue that might require further triage, it can call **StorPortCaptureLiveDump** to capture a live dump file.

This function must be called at PASSIVE_LEVEL.

## -see-also

[**STOR_ADDRESS**](ns-storport-_stor_address.md)

[**STORPORT_CAPTURE_LIVEDUMP**](ns-storport-storport_capture_livedump.md)

[**STORPORT_LIVEDUMP_DATA_TYPE**](ne-storport-storport_livedump_data_type.md)

[**STORPORT_LIVEDUMP_DEVICE_TELEMETRY_LOG**](ns-storport-storport_livedump_device_telemetry_log.md)
