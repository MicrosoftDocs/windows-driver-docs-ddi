---
UID: NF:storport.StorPortNvmeMiniportEvent
tech.root: storage
title: StorPortNvmeMiniportEvent
ms.date: 07/25/2024
targetos: Windows
description: Learn more about the StorPortNvmeMiniportEvent function.
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
 - StorPortNvmeMiniportEvent
f1_keywords:
 - StorPortNvmeMiniportEvent
 - storport/StorPortNvmeMiniportEvent
dev_langs:
 - c++
helpviewer_keywords:
 - StorPortNvmeMiniportEvent
---

## -description

An NVMe miniport driver calls the **StorPortNvmeMiniportEvent** function to log an ETW event to a specific channel with up to eight extra general purpose parameters.

## -parameters

### -param HwDeviceExtension

[in] A pointer to the hardware device extension for the host bus adapter (HBA).

### -param ControllerHandle

[in/optional] For a fabric NVMe (NVMe-oF) miniport, if the event is controller-specific, **ControllerHandle** is Storport's handle for the NVMe controller; otherwise, the value is NULL.

### -param NamespaceId

[in] If the event is namespace-specific, **NamespaceId** is the namespace identifier; otherwise, it should be zero.

### -param EventChannel

[in] A [**STORPORT_ETW_EVENT_CHANNEL**](ne-storport-storport_etw_event_channel.md) enumeration value that specifies the ETW channel where the event is logged.

### -param EventId

[in] Minipoort-specific event identifier to uniquely identify the type of event.

### -param EventDescription

[in] Required string that describes the event. The maximum size of the string is **STORPORT_ETW_MAX_DESCRIPTION_LENGTH** characters, not including the null terminator.

### -param EventKeywords

[in] Bitmask of STORPORT_ETW_EVENT_CHANNEL_*XXX* values to further characterize the event. Set to zero if no keywords are needed.

### -param EventLevel

[in] A [**STORPORT_ETW_LEVEL**](ne-storport-storport_etw_level.md) value that specifies the level of the event.

### -param EventOpcode

[in] A [**STORPORT_ETW_EVENT_OPCODE**](ne-storport-storport_etw_event_opcode.md) enumeration value that specifies the opcode of the event.

### -param Parameter1Name

[in] A short string that gives meaning to **Parameter1Value**. If **Parameter1Name** is NULL or an empty string, **Parameter1Value** is ignored. The maximum size of the string is **STORPORT_ETW_MAX_PARAM_NAME_LENGTH** characters, not including the null terminator.

### -param Parameter1Value

[in] The value of the first parameter. If **Parameter1Name** is NULL or an empty string, Storport will log this value as zero.

### -param Parameter2Name

[in] A short string that gives meaning to **Parameter2Value**. If **Parameter2Name** is NULL or an empty string, **Parameter2Value** is ignored. The maximum size of the string is **STORPORT_ETW_MAX_PARAM_NAME_LENGTH** characters, not including the null terminator.

### -param Parameter2Value

[in] The value of the second parameter. If **Parameter2Name** is NULL or an empty string, Storport will log this value as zero.

### -param Parameter3Name

[in] A short string that gives meaning to **Parameter3Value**. If **Parameter3Name** is NULL or an empty string, **Parameter3Value** is ignored. The maximum size of the string is **STORPORT_ETW_MAX_PARAM_NAME_LENGTH** characters, not including the null terminator.

### -param Parameter3Value

[in] The value of the third parameter. If **Parameter3Name** is NULL or an empty string, Storport will log this value as zero.

### -param Parameter4Name

[in] A short string that gives meaning to **Parameter4Value**. If **Parameter4Name** is NULL or an empty string, **Parameter4Value** is ignored. The maximum size of the string is **STORPORT_ETW_MAX_PARAM_NAME_LENGTH** characters, not including the null terminator.

### -param Parameter4Value

[in] The value of the fourth parameter. If **Parameter4Name** is NULL or an empty string, Storport will log this value as zero.

### -param Parameter5Name

[in] A short string that gives meaning to **Parameter5Value**. If **Parameter5Name** is NULL or an empty string, **Parameter5Value** is ignored. The maximum size of the string is **STORPORT_ETW_MAX_PARAM_NAME_LENGTH** characters, not including the null terminator.

### -param Parameter5Value

[in] The value of the fifth parameter. If **Parameter5Name** is NULL or an empty string, Storport will log this value as zero.

### -param Parameter6Name

[in] A short string that gives meaning to **Parameter6Value**. If **Parameter6Name** is NULL or an empty string, **Parameter6Value** is ignored. The maximum size of the string is **STORPORT_ETW_MAX_PARAM_NAME_LENGTH** characters, not including the null terminator.

### -param Parameter6Value

[in] The value of the sixth parameter. If **Parameter6Name** is NULL or an empty string, Storport will log this value as zero.

### -param Parameter7Name

[in] A short string that gives meaning to **Parameter7Value**. If **Parameter7Name** is NULL or an empty string, **Parameter7Value** is ignored. The maximum size of the string is **STORPORT_ETW_MAX_PARAM_NAME_LENGTH** characters, not including the null terminator.

### -param Parameter7Value

[in] The value of the seventh parameter. If **Parameter7Name** is NULL or an empty string, Storport will log this value as zero.

### -param Parameter8Name

[in] A short string that gives meaning to **Parameter8Value**. If **Parameter8Name** is NULL or an empty string, **Parameter8Value** is ignored. The maximum size of the string is **STORPORT_ETW_MAX_PARAM_NAME_LENGTH** characters, not including the null terminator.

### -param Parameter8Value

[in] The value of the eighth parameter. If **Parameter8Name** is NULL or an empty string, Storport will log this value as zero.

## -returns

**StorPortNvmeMiniportEvent** returns a STOR_STATUS_SUCCESS if the event is successfully logged. Otherwise, it returns a value such as:

| Return code | Description |
| ----------- | ----------- |
| **STOR_STATUS_NOT_IMPLEMENTED** | This function is not implemented on the active operating system. |
| **STOR_STATUS_INVALID_PARAMETER** | The operation fails with this return value if one or more of the parameters are invalid. |
| **STOR_STATUS_UNSUCCESSFUL** | The operation failed for other internal reasons. |

## -remarks

A miniport can call **StorPortNvmeMiniportEvent** to log eight general-purpose ETW parameters. The ETW parameters are expressed as eight name-value pairs. If a parameter is not named (Parameter*X*Name = NULL), the routine will set the corresponding parameter value to 0.

Events generated from StorPort miniport drivers are logged in the channel specified by **EventChannel**.

## -see-also

[**STORPORT_ETW_EVENT_CHANNEL**](ne-storport-storport_etw_event_channel.md)

[**STORPORT_ETW_LEVEL**](ne-storport-storport_etw_level.md)

[**STORPORT_ETW_EVENT_OPCODE**](ne-storport-storport_etw_event_opcode.md)
