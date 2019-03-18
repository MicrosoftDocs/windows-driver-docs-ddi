---
UID: NS:ntddk._CUSTOM_SYSTEM_EVENT_TRIGGER_CONFIG
title: _CUSTOM_SYSTEM_EVENT_TRIGGER_CONFIG (ntddk.h)
description: Contains information about a custom system event trigger.
ms.assetid: 08c4b025-930e-4348-9fc2-a41fcfa33c0d
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _CUSTOM_SYSTEM_EVENT_TRIGGER_CONFIG, CUSTOM_SYSTEM_EVENT_TRIGGER_CONFIG, *PCUSTOM_SYSTEM_EVENT_TRIGGER_CONFIG, 
req.header: ntddk.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: CUSTOM_SYSTEM_EVENT_TRIGGER_CONFIG, *PCUSTOM_SYSTEM_EVENT_TRIGGER_CONFIG
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- ntddk.h
api_name: 
- _CUSTOM_SYSTEM_EVENT_TRIGGER_CONFIG
product:
- Windows
targetos: Windows
---

# _CUSTOM_SYSTEM_EVENT_TRIGGER_CONFIG structure

## -description
Contains information about a custom system event trigger. This structure is used by [**RtlRaiseCustomSystemEventTrigger**](nf-ntddk-rtlraisecustomsystemeventtrigger.md).

## -struct-fields

### -field Size
The size of the structure in bytes.

### -field TriggerId
 
A pointer to a Unicode string that contains the GUID used to identify background task to trigger.

## -remarks
To initialize this structure, call [**CUSTOM_SYSTEM_EVENT_TRIGGER_INIT**](nf-ntddk-custom_system_event_trigger_init.md).

## -see-also
[**RtlRaiseCustomSystemEventTrigger**](nf-ntddk-rtlraisecustomsystemeventtrigger.md)

[**CUSTOM_SYSTEM_EVENT_TRIGGER_INIT**](nf-ntddk-custom_system_event_trigger_init.md)
