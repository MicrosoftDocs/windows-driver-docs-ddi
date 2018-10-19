---
UID: NF:ntddk.CUSTOM_SYSTEM_EVENT_TRIGGER_INIT
title: CUSTOM_SYSTEM_EVENT_TRIGGER_INIT function
author: windows-driver-content
description: Initializes the [**_CUSTOM_SYSTEM_EVENT_TRIGGER_CONFIG**](ns-ntddk-_custom_system_event_trigger_config.md) structure.
ms.assetid: 27fda9f0-940d-441a-a4bc-ccb65f27b7f3
ms.date: 10/19/2018
ms.topic: function
ms.keywords: CUSTOM_SYSTEM_EVENT_TRIGGER_INIT
req.header: ntddk.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
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
topictype: 
-	apiref
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	CUSTOM_SYSTEM_EVENT_TRIGGER_INIT
product:
-	Windows
targetos: Windows

---

# CUSTOM_SYSTEM_EVENT_TRIGGER_INIT function


## -description

Initializes the [**_CUSTOM_SYSTEM_EVENT_TRIGGER_CONFIG**](ns-ntddk-_custom_system_event_trigger_config.md) structure.

## -parameters

### -param Config
A pointer to the [**_CUSTOM_SYSTEM_EVENT_TRIGGER_CONFIG**](ns-ntddk-_custom_system_event_trigger_config.md) structure to initialize.

### -param TriggerId
A pointer to a Unicode string that contains the GUID used to identify background task to trigger.

## -returns
This function returns VOID.

## -remarks

## -see-also

[**_CUSTOM_SYSTEM_EVENT_TRIGGER_CONFIG**](ns-ntddk-_custom_system_event_trigger_config.md)

[**RtlRaiseCustomSystemEventTrigger**](nf-ntddk-rtlraisecustomsystemeventtrigger.md)

