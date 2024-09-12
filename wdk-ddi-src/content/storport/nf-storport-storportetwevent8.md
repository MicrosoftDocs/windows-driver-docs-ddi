---
UID: NF:storport.StorPortEtwEvent8
title: StorPortEtwEvent8 function (storport.h)
description: Learn more about the StorPortEtwEvent8 function.
tech.root: storage
ms.date: 07/25/2024
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
 - StorPortEtwEvent8
 - storport/StorPortEtwEvent8
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortEtwEvent8
---

# StorPortEtwEvent8 function

## -description

A miniport calls **StorPortEtwEvent8** to log an ETW event with eight general-purpose ETW parameters to a storage trace channel.

## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).

### -param Address [in/optional]

The storage unit device address. This parameter is NULL for adapter devices.

### -param EventId [in]

A miniport-defined identifier to uniquely identify the type of event.

### -param EventDescription [in]

Required string that describes the event. The maximum size of the string is **STORPORT_ETW_MAX_DESCRIPTION_LENGTH** characters, not including the null terminator.

### -param EventKeywords [in]

Keyword flags for event categorization. Set to 0 if no keyword is desired. The keywords are a bitwise OR combination of the following.

| Value | Meaning |
| ----- | ------- |
| STORPORT_ETW_EVENT_KEYWORD_IO | The event is related to device IO operations. |
| STORPORT_ETW_EVENT_KEYWORD_PERFORMANCE | The event is performance related. |
| STORPORT_ETW_EVENT_KEYWORD_POWER | The event is related to device power. |
| STORPORT_ETW_EVENT_KEYWORD_ENUMERATION | The event is related to device enumeration. |

### -param EventLevel [in]

A [**STORPORT_ETW_LEVEL**](ne-storport-storport_etw_level.md) value that specifies the importance or severity of the event.

### -param EventOpcode [in]

A [**STORPORT_ETW_EVENT_OPCODE**](ne-storport-storport_etw_event_opcode.md) value that specifies the operational nature of the event.

### -param Srb [in/optional]

A pointer to the SRB associated with the logged event. If this parameter contains a valid SRB, this SRB pointer and the associated SRB pointer are logged.

### -param Parameter1Name [in/optional]

A description of the meaning of **Parameter1Value**. The maximum size of the string is **STORPORT_ETW_MAX_PARAM_NAME_LENGTH** characters, not including the null terminator.

### -param Parameter1Value [in]

The value for parameter 1.

### -param Parameter2Name [in/optional]

A description of the meaning of **Parameter2Value**. The maximum size of the string is **STORPORT_ETW_MAX_PARAM_NAME_LENGTH** characters, not including the null terminator.

### -param Parameter2Value [in]

The value for parameter 2.

### -param Parameter3Name [in/optional]

A description of the meaning of **Parameter3Value**. The maximum size of the string is **STORPORT_ETW_MAX_PARAM_NAME_LENGTH** characters, not including the null terminator.

### -param Parameter3Value [in]

The value for parameter 3.

### -param Parameter4Name [in/optional]

A description of the meaning of **Parameter4Value**. The maximum size of the string is **STORPORT_ETW_MAX_PARAM_NAME_LENGTH** characters, not including the null terminator.

### -param Parameter4Value [in]

The value for parameter 4.

### -param Parameter5Name [in/optional]

A description of the meaning of **Parameter5Value**. The maximum size of the string is **STORPORT_ETW_MAX_PARAM_NAME_LENGTH** characters, not including the null terminator.

### -param Parameter5Value [in]

The value for parameter 5.

### -param Parameter6Name [in/optional]

A description of the meaning of **Parameter6Value**. The maximum size of the string is **STORPORT_ETW_MAX_PARAM_NAME_LENGTH** characters, not including the null terminator.

### -param Parameter6Value [in]

The value for parameter 6.

### -param Parameter7Name [in/optional]

A description of the meaning of **Parameter7Value**. The maximum size of the string is **STORPORT_ETW_MAX_PARAM_NAME_LENGTH** characters, not including the null terminator.

### -param Parameter7Value [in]

The value for parameter 7.

### -param Parameter8Name [in/optional]

A description of the meaning of **Parameter8Value**. The maximum size of the string is **STORPORT_ETW_MAX_PARAM_NAME_LENGTH** characters, not including the null terminator.

### -param Parameter8Value [in]

The value for parameter 8.

## -returns

**StorPortEtwEvent8** returns one of the following status codes:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_SUCCESS | The event was successfully logged. |
| STOR_STATUS_NOT_IMPLEMENTED | Tracing is not enabled for storage events. |
| STOR_STATUS_INVALID_PARAMETER | One of the parameters is invalid. For example, **HwDeviceExtension** or **EventDescription** are NULL, **EventDescription** is greater than the maximum name length, or an ETW parameter name is greater than the maximum name length. |

## -remarks

A miniport can call **StorPortEtwEvent8** to log eight general-purpose ETW parameters. The ETW parameters are expressed as eight name-value pairs. If a parameter is not named (Parameter*X*Name = NULL), the routine will set the corresponding parameter value to 0.

Events generated from StorPort miniport drivers are logged to the "Microsoft-Windows-Storage-Storport/Diagnose" ETW channel.

## -see-also

[**StorPortNvmeMiniportEvent**](nf-storport-storportnvmeminiportevent.md)

[**StorPortEtwChannelEvent2**](nf-storport-storportetwchannelevent2.md)

[**StorPortEtwChannelEvent4**](nf-storport-storportetwchannelevent4.md)

[**StorPortEtwChannelEvent8**](nf-storport-storportetwchannelevent8.md)

[**StorPortEtwEvent2**](nf-storport-storportetwevent2.md)

[**StorPortEtwEvent4**](nf-storport-storportetwevent4.md)

[**StorPortEtwLogByteStream**](nf-storport-storportetwlogbytestream.md)

[**StorPortEtwLogError**](nf-storport-storportetwlogerror.md)
