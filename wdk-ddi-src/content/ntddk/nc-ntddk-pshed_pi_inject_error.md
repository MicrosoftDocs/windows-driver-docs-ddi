---
UID: NC:ntddk.PSHED_PI_INJECT_ERROR
title: PSHED_PI_INJECT_ERROR (ntddk.h)
description: A PSHED plug-in's InjectError callback function injects an error into the hardware platform.
tech.root: whea
ms.date: 12/06/2022
keywords: ["PSHED_PI_INJECT_ERROR callback function"]
ms.keywords: InjectError, InjectError callback function [WHEA Drivers and Applications], PSHED_PI_INJECT_ERROR, PSHED_PI_INJECT_ERROR callback, ntddk/InjectError, whea.injecterror, whearef_377f07ab-4ea0-4982-8298-c7139b4bfdc7.xml
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.irql: IRQL = DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PSHED_PI_INJECT_ERROR
 - ntddk/PSHED_PI_INJECT_ERROR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ntddk.h
api_name:
 - PSHED_PI_INJECT_ERROR
---

## -description

A PSHED plug-in's *InjectError* callback function injects an error into the hardware platform.

## -parameters

### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the **Context** member of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure when the PSHED plug-in called the [PshedRegisterPlugin](./nf-ntddk-pshedregisterplugin.md) function to register itself with the PSHED.

### -param ErrorType [in]

The type of error to be injected into the hardware platform. Possible values are:

#### INJECT_ERRTYPE_PROCESSOR_CORRECTABLE

A correctable processor error.

#### INJECT_ERRTYPE_PROCESSOR_UNCORRECTABLENONFATAL

An uncorrectable nonfatal processor error.

#### INJECT_ERRTYPE_PROCESSOR_UNCORRECTABLEFATAL

An uncorrectable fatal processor error.

#### INJECT_ERRTYPE_MEMORY_CORRECTABLE

A correctable memory error.

#### INJECT_ERRTYPE_MEMORY_UNCORRECTABLENONFATAL

An uncorrectable nonfatal memory error.

#### INJECT_ERRTYPE_MEMORY_UNCORRECTABLEFATAL

An uncorrectable fatal memory error.

#### INJECT_ERRTYPE_PCIEXPRESS_CORRECTABLE

A correctable PCI Express error.

#### INJECT_ERRTYPE_PCIEXPRESS_UNCORRECTABLENONFATAL

An uncorrectable nonfatal PCI Express error.

#### INJECT_ERRTYPE_PCIEXPRESS_UNCORRECTABLEFATAL

An uncorrectable fatal PCI Express error.

#### INJECT_ERRTYPE_PLATFORM_CORRECTABLE

A correctable platform error.

#### INJECT_ERRTYPE_PLATFORM_UNCORRECTABLENONFATAL

An uncorrectable nonfatal platform error.

#### INJECT_ERRTYPE_PLATFORM_UNCORRECTABLEFATAL

An uncorrectable fatal platform error.

### -param Parameter1 [in]

A generic parameter that contains additional data that is passed by the WHEA management application that is injecting the error.

### -param Parameter2 [in]

A generic parameter that contains additional data that is passed by the WHEA management application that is injecting the error.

### -param Parameter3 [in]

A generic parameter that contains additional data that is passed by the WHEA management application that is injecting the error.

### -param Parameter4 [in]

A generic parameter that contains additional data that is passed by the WHEA management application that is injecting the error.

## -returns

A PSHED plug-in's *InjectError* callback function returns one of the following NTSTATUS codes:

| Return code | Description |
|---|---|
| **STATUS_SUCCESS** | The error was successfully injected into the hardware platform. |
| **STATUS_UNSUCCESSFUL** | An error occurred. For injected errors that are fatal or otherwise unrecoverable, this callback function might not return before the operating system generates a bug check in response to the error condition. |

## -remarks

A PSHED plug-in that participates in error injection sets the **Callbacks.GetInjectionCapabilities** and **Callbacks.InjectError** members of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure to point to its [GetInjectionCapabilities](./nc-ntddk-pshed_pi_get_injection_capabilities.md) and *InjectError* callback functions when the plug-in calls the [PshedRegisterPlugin](./nf-ntddk-pshedregisterplugin.md) function to register itself with the PSHED. The PSHED plug-in must also set the **PshedFAErrorInjection** flag in the **FunctionalAreaMask** member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

When a WHEA management application makes a request to inject a hardware error, the Windows kernel calls into the PSHED to inject the error into the hardware platform. If a PSHED plug-in is registered to participate in error injection, the PSHED calls the PSHED plug-in's *InjectError* callback function to perform the error injection operation.

The WHEA management application that is injecting the error can pass additional error-specific data to the PSHED plug-in's *InjectError* callback function by using parameters *Parameter1* through *Parameter4*. For example, on Itanium-based systems, some of the error injection operations require an accompanying address. In this situation, the WHEA management application can pass the address to the PSHED plug-in's *InjectError* callback function using one of these parameters.

## -see-also

[GetInjectionCapabilities](./nc-ntddk-pshed_pi_get_injection_capabilities.md)

[PshedRegisterPlugin](./nf-ntddk-pshedregisterplugin.md)

[**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet)