---
UID: NF:storport.StorPortNvmeLogTelemetry
tech.root: storage
title: StorPortNvmeLogTelemetry
ms.date: 07/25/2024
targetos: Windows
description: Learn more about the StorPortNvmeLogTelemetry function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
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
 - StorPortNvmeLogTelemetry
f1_keywords:
 - StorPortNvmeLogTelemetry
 - storport/StorPortNvmeLogTelemetry
dev_langs:
 - c++
helpviewer_keywords:
 - StorPortNvmeLogTelemetry
---

## -description

An NMVe miniport driver calls the **StorPortNvmeLogTelemetry** function to log telemetry events for an NVMe device.

## -parameters

### -param HwDeviceExtension

[in] A pointer to the hardware device extension for the host bus adapter (HBA).

### -param ControllerHandle

[in/optional] For a fabric NVMe miniport, if the event is controller-specific, **ControllerHandle** is StorPort's handle for the NVMe controller. Otherwise, **ControllerHandle** should be NULL.

### -param NamespaceId

[in] If the event is namespace-specific, **NamespaceId** is the namespace identifier. Otherwise, **NamespaceId** should be 0.

### -param Event

[in] Pointer to a [**STORPORT_TELEMTRY_EVENT**](ns-storport-_storport_telemetry_event.md) structure that contains standard event fields and miniport payload data.

### -param Category

[in] A [**STOR_TELEMETRY_CATEGORY**](ne-storport-_stor_telemetry_category.md) value that specifies the telemetry category to log.

## -returns

**StorPortNvmeLogTelemetry** returns **STOR_STATUS_SUCCESS** if the telemetry event is successfully logged. Otherwise, it returns a STOR_STATUS error code such as the following:

| Return code | Description |
| ----------- | ----------- |
| **STOR_STATUS_NOT_IMPLEMENTED** | This function is not implemented on the active operating system. |
| **STOR_STATUS_INVALID_PARAMETER** | The operation fails with this return value if one or more of the parameters are invalid. |

## -remarks

An NVMe miniport can call this function to log a tracelogging measures event with miniport-customized data that is encapsulated in **Event**.

**StorPortNvmeLogTelemetry** additionally allows the caller to specify a telemtry category type.

## -see-also

[**STOR_TELEMETRY_CATEGORY**](ne-storport-_stor_telemetry_category.md)

[**STORPORT_TELEMTRY_EVENT**](ns-storport-_storport_telemetry_event.md)
