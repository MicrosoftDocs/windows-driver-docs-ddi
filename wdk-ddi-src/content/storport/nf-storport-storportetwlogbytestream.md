---
UID: NF:storport.StorPortEtwLogByteStream
tech.root: storage
title: StorPortEtwLogByteStream
ms.date: 05/13/2021
targetos: Windows
description: StorPortEtwLogByteStream logs an Event Tracing for Windows (ETW) event with a general purpose byte stream parameter to the specified channel.
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
 - StorPortEtwLogByteStream
f1_keywords:
 - StorPortEtwLogByteStream
 - storport/StorPortEtwLogByteStream
dev_langs:
 - c++
---

## -description

**StorPortEtwLogByteStream** logs an Event Tracing for Windows (ETW) event with a general purpose byte stream parameter to the specified channel.

## -parameters

### -param HwDeviceExtension

[in] A pointer to the miniport's device extension.

### -param Address

[in, optional] The storage unit device address. This parameter is NULL for adapter devices.

### -param EventChannel

[in] A [**STORPORT_ETW_EVENT_CHANNEL**](ne-storport-storport_etw_event_channel.md) value that identifies the ETW channel in which to log the event.

### -param EventId

[in] A miniport-defined event ID that uniquely identifies the event.

### -param EventDescription

[in] A short string describing the event. *EventDescription* is required and must be <= STORPORT_ETW_MAX_DESCRIPTION_LENGTH characters, not including the NULL terminator.

### -param EventKeywords

[in] Keyword flags for event categorization. Set to 0 if no keyword is desired. The keywords are a bitwise OR combination of the following.

| Value | Meaning |
| ----- | ------- |
| STORPORT_ETW_EVENT_KEYWORD_IO | The event is related to device IO operations. |
| STORPORT_ETW_EVENT_KEYWORD_PERFORMANCE | The event is performance related. |
| STORPORT_ETW_EVENT_KEYWORD_POWER | The event is related to device power. |
| STORPORT_ETW_EVENT_KEYWORD_ENUMERATION | The event is related to device enumeration. |

### -param EventLevel

[in] The event level. This value can indicate the importance or severity of the event. This is one of the following values.

| Value | Meaning |
| ----- | ------- |
| StorportEtwLevelLogAlways | Log the event unconditionally. The event is logged regardless of any filters set. |
| StorportEtwLevelCritical | Critical level event. |
| StorportEtwLevelError | Error level event. |
| StorportEtwLevelWarning | Warning level event. |
| StorportEtwLevelInformational | Informational event. |
| StorportEtwLevelVerbose | Verbose event information provided. |

### -param EventOpcode

[in] The operational nature of the event. This is one of the following values.

| Value | Meaning |
| ----- | ------- |
| StorportEtwEventOpcodeInfo | General informational event. |
| StorportEtwEventOpcodeStart | Device or unit was starting. |
| StorportEtwEventOpcodeStop | Device or unit was stopping. The event corresponds to the last unpaired start event. |
| StorportEtwEventOpcodeDC_Start | A data collection starting event. These are rundown event types. |
| StorportEtwEventOpcodeDC_Stop | A data collection stopping event. These are rundown event types. |
| StorportEtwEventOpcodeExtension | An extension event. |
| StorportEtwEventOpcodeReply | A reply event. |
| StorportEtwEventOpcodeResume | Device or unit was resuming after suspend. |
| StorportEtwEventOpcodeSuspend | Device or unit is suspended pending completion of another operation. |
| StorportEtwEventOpcodeReceive | Transfer of activity is received from another component. |

### -param DataLength

[in] Length, in bytes, of the byte stream that *Data* points to, where 1 <= *DataLength* <= STORPORT_ETW_MAX_BYTE_STREAM_LENGTH.

### -param Data

[in] Pointer to the miniport's custom ETW byte stream.

## -returns

**StorPortEtwLogByteStream** returns one of the following status codes:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_SUCCESS | The event was successfully logged to the specified ETW channel. |
| STOR_STATUS_INVALID_PARAMETER | A parameter is invalid. For example, *HwDeviceExtension*,  *EventDescription*, or *Data* are NULL, *DataLength* is greater than the maximum name length, *EventChannel* is an invalid value. |
| STOR_STATUS_UNSUCCESSFUL | Returned for other internal reasons. |

## -remarks

A miniport can call **StorPortEtwLogByteStream** to log an ETW event to a specific channel with a general purpose byte stream parameter.

**StorPortEtwLogByteStream** is useful when a miniport needs to log context beyond that allowed in [**StorPortEtwEvent2**](./nf-storport-storportetwevent2.md), [**StorPortEtwEvent4**](./nf-storport-storportetwevent4.md), or [**StorPortEtwEvent8**](./nf-storport-storportetwevent8.md). For instance, a miniport can log its internal data structure as a byte stream that can then be used for diagnostic purposes when issues get reported.

## -see-also

[**StorPortEtwEvent2**](./nf-storport-storportetwevent2.md)

[**StorPortEtwEvent4**](./nf-storport-storportetwevent4.md)

[**StorPortEtwEvent8**](./nf-storport-storportetwevent8.md)

[**StorPortEtwLogError**](nf-storport-storportetwlogerror.md)
