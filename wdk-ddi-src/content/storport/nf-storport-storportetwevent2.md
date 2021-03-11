---
UID: NF:storport.StorPortEtwEvent2
title: StorPortEtwEvent2 function (storport.h)
description: StorPortEtwEvent2 logs an Event Tracing for Windows (ETW) event with two general-purpose ETW parameters to a storage trace channel.
old-location: storage\storportetwevent2.htm
tech.root: storage
ms.date: 05/13/2021
keywords: ["StorPortEtwEvent2 function"]
ms.keywords: STORPORT_ETW_EVENT_KEYWORD_ENUMERATION, STORPORT_ETW_EVENT_KEYWORD_IO, STORPORT_ETW_EVENT_KEYWORD_PERFORMANCE, STORPORT_ETW_EVENT_KEYWORD_POWER, StorPortEtwEvent2, StorPortEtwEvent2 routine [Storage Devices], StorportEtwEventOpcodeDC_Start, StorportEtwEventOpcodeDC_Stop, StorportEtwEventOpcodeExtension, StorportEtwEventOpcodeInfo, StorportEtwEventOpcodeReceive, StorportEtwEventOpcodeReply, StorportEtwEventOpcodeResume, StorportEtwEventOpcodeStart, StorportEtwEventOpcodeStop, StorportEtwEventOpcodeSuspend, StorportEtwLevelCritical, StorportEtwLevelError, StorportEtwLevelInformational, StorportEtwLevelLogAlways, StorportEtwLevelVerbose, StorportEtwLevelWarning, storage.storportetwevent2, storport/StorPortEtwEvent2
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortEtwEvent2
 - storport/StorPortEtwEvent2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortEtwEvent2
---

# StorPortEtwEvent2 function

## -description

**StorPortEtwEvent2** logs an Event Tracing for Windows (ETW) event with two general-purpose ETW parameters to a storage trace channel.

## -parameters

### -param HwDeviceExtension

[in] A pointer to the miniport's device extension.

### -param Address

[in, optional] The storage unit device address. This parameter is NULL for adapter devices.

### -param EventId

[in] A miniport-defined identifier for the ETW event.

### -param EventDescription

[in] The description text for the event. This text string must be <= STORPORT_ETW_MAX_DESCRIPTION_LENGTH.

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

### -param Srb

[in, optional] A pointer to the SRB associated with the logged event. If this parameter contains a valid SRB, this SRB pointer and the associated SRB pointer are logged.

### -param Parameter1Name

[in, optional] A description of the meaning of *Parameter1Value*. This parameter name string must be <= STORPORT_ETW_MAX_PARAM_NAME_LENGTH.

### -param Parameter1Value

[in] The value for parameter 1.

### -param Parameter2Name

[in, optional] A description of the meaning of *Parameter2Value*. This parameter name string must be <= STORPORT_ETW_MAX_PARAM_NAME_LENGTH.

### -param Parameter2Value

[in] The value for parameter 2.

## -returns

**StorPortEtwEvent2** returns one of the following status codes:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_SUCCESS | The event was successfully logged. |
| STOR_STATUS_NOT_IMPLEMENTED | Tracing is not enabled for storage events. |
| STOR_STATUS_INVALID_PARAMETER | One of the parameters is invalid. For example, *HwDeviceExtension* or *EventDescription* are NULL, *EventDescription* is greater than the maximum name length, or an ETW parameter name is greater than the maximum name length. |

## -remarks

A miniport can call **StorPortEtwEvent2** to log two general-purpose ETW parameters. The ETW parameters are expressed as two name-value pairs. If a parameter is not named (Parameter*X*Name = NULL), the routine will set the corresponding parameter value to 0.

Events generated from StorPort miniport drivers are logged to the "Microsoft-Windows-Storage-Storport/Diagnose" ETW channel.

## -see-also

[**StorPortEtwEvent4**](nf-storport-storportetwevent4.md)

[**StorPortEtwEvent8**](nf-storport-storportetwevent8.md)

[**StorPortEtwLogByteStream**](nf-storport-storportetwlogbytestream.md)

[**StorPortEtwLogError**](nf-storport-storportetwlogerror.md)
