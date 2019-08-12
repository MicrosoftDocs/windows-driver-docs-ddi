---
UID: NF:storport.StorPortLogTelemetryEx
title: StorPortLogTelemetryEx function
author: windows-driver-content
description: The StorPortLogTelemetry routine logs a miniport telemetry event to help diagnose or collect any useful information.
tech.root: storage
ms.assetid: a4b538e9-f121-4081-9b01-2a9b38c1e266
ms.author: windowsdriverdev
ms.date: 03-05-2019
ms.topic: function
f1_keywords:
 - "storport/StorPortLogTelemetryEx"
ms.keywords: StorPortLogTelemetryEx, STOR_TELEMETRY_CATEGORY, STORPORT_TELEMETRY_EVENT, StorPortLogTelemetry
req.header: storport.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- LibDef
api_location:
- storport.h
api_name: 
- StorPortLogTelemetryEx
product: Windows
targetos: Windows

ms.custom: 19H1
---

# StorPortLogTelemetryEx function

## -description

The **StorPortLogTelemetry** routine logs a miniport telemetry event to help diagnose or collect any useful information.

## -parameters

### -param HwDeviceExtension

Pointer to the hardware device extension for the host bus adapter (HBA).

### -param StorAddress

Storage unit device address. This parameter is NULL for adapter devices.

### -param Event

Pointer to the [STORPORT_TELEMETRY_EVENT](ns-storport-_storport_telemetry_event.md) structure that contains the telemetry data payload.

### -param Category

[STOR_TELEMETRY_CATEGORY](ne-storport-_stor_telemetry_category.md) enum value that specifies the category of telemetry to be logged.

## -returns

**StorPortLogTelemetryEx** returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_BUFFER_SIZE</b></dt>
</dl>
</td>
<td width="60%">
<b>Event->EventBufferLength</b> is larger than <b>EVENT_BUFFER_MAX_LENGTH</b>.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A pointer to one of the parameters is NULL or the EventBufferLength is set to zero for a non-NULL <b>Event->EventBuffer</b>.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The telemetry event was successfully logged.

</td>
</tr>
</table>

## -remarks

A miniport can call **StorPortLogTelemetryEx** to log a tracelogging measures or telemetry event with miniport-customized data. Miniports specify the event category type in *Category*.

The event data is encapsulated in the [STORPORT_TELEMETRY_EVENT](ns-storport-_storport_telemetry_event.md) structure to which *Event* points. The miniport can log eight general purpose name-value pairs and a buffer that has a maximum length of 4KB, as well as several event-related fields.

## -see-also

[STOR_TELEMETRY_CATEGORY](ne-storport-_stor_telemetry_category.md)

[STORPORT_TELEMETRY_EVENT](ns-storport-_storport_telemetry_event.md)

[StorPortLogTelemetry](nf-storport-storportlogtelemetry.md)
