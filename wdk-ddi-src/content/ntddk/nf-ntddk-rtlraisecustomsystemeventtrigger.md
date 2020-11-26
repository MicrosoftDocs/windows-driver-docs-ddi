---
UID: NF:ntddk.RtlRaiseCustomSystemEventTrigger
title: RtlRaiseCustomSystemEventTrigger function (ntddk.h)
description: Allows NT services and kernel-mode and user-mode drivers to raise a custom trigger for a device.
ms.assetid: b5f212a3-3b2a-46ce-ae89-112320d0b2a9
ms.date: 10/19/2018
tech.root: kernel
keywords: ["RtlRaiseCustomSystemEventTrigger function"]
ms.keywords: RtlRaiseCustomSystemEventTrigger
req.header: ntddk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - RtlRaiseCustomSystemEventTrigger
 - ntddk/RtlRaiseCustomSystemEventTrigger
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlRaiseCustomSystemEventTrigger
---

# RtlRaiseCustomSystemEventTrigger function


## -description

Allows NT services and kernel-mode and user-mode drivers to raise a custom trigger for a device. A custom trigger, owned by the driver developer, notifies system event broker to start an associated background task with it, which is identified by a custom trigger identifier.

## -parameters

### -param TriggerConfig

[_In_] A pointer to a [**_CUSTOM_SYSTEM_EVENT_TRIGGER_CONFIG**](ns-ntddk-_custom_system_event_trigger_config.md) structure that contains the trigger identifier. Call [**CUSTOM_SYSTEM_EVENT_TRIGGER_INIT**](nf-ntddk-custom_system_event_trigger_init.md) to initialize the structure before calling the function.

## -returns

This function returns STATUS_SUCCESS if the custom trigger was raised. Otherwise, an appropriate [NTSTATUS Value](/windows-hardware/drivers/kernel/ntstatus-values) is returned.

| Error code                    | Description                                 |
| ----------------------------- | ------------------------------------------- |
| STATUS_UNSUCCESSFUL           | Another active custom trigger being raised. |
| STATUS_INSTANCE_NOT_AVAILABLE | No subscribers are present.                 |

## -remarks

## -see-also

[**_CUSTOM_SYSTEM_EVENT_TRIGGER_CONFIG**](ns-ntddk-_custom_system_event_trigger_config.md)
[**CUSTOM_SYSTEM_EVENT_TRIGGER_INIT**](nf-ntddk-custom_system_event_trigger_init.md)
