---
UID: NC:ntddk.PSHED_PI_DISABLE_ERROR_SOURCE
title: PSHED_PI_DISABLE_ERROR_SOURCE (ntddk.h)
description: A PSHED plug-in's DisableErrorSource callback function disables an error source.
tech.root: whea
ms.date: 04/17/2023
keywords: ["PSHED_PI_DISABLE_ERROR_SOURCE callback function"]
ms.keywords: DisableErrorSource, DisableErrorSource callback function [WHEA Drivers and Applications], PSHED_PI_DISABLE_ERROR_SOURCE, PSHED_PI_DISABLE_ERROR_SOURCE callback, ntddk/DisableErrorSource, whea.disableerrorsource, whearef_41df46d2-6f6e-47aa-8296-cdc9223a9f26.xml
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt:
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
 - PSHED_PI_DISABLE_ERROR_SOURCE
 - ntddk/PSHED_PI_DISABLE_ERROR_SOURCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ntddk.h
api_name:
 - PSHED_PI_DISABLE_ERROR_SOURCE
---

## -description

A PSHED plug-in's *DisableErrorSource* callback function disables an error source.

## -parameters

### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the **Context** member of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure when the PSHED plug-in called the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED.

### -param ErrorSource [in]

A pointer to a [**WHEA_ERROR_SOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor) structure that describes the error source that is being disabled.

## -returns

A PSHED plug-in's *DisableErrorSource* callback function returns one of the following NTSTATUS codes:

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | The error source was successfully disabled. |
| **STATUS_NOT_SUPPORTED** | The PSHED plug-in does not support disabling the specified error source. |
| **STATUS_UNSUCCESSFUL** | An error occurred. |

## -remarks

A PSHED plug-in that participates in error source control sets the **Callbacks.SetErrorSourceInfo**, **Callbacks.EnableErrorSource**, and **Callbacks.DisableErrorSource** members of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure to point to its [SetErrorSourceInfo](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_set_error_source_info), [EnableErrorSource](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_enable_error_source), and *DisableErrorSource* callback functions when the plug-in calls the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED. The PSHED plug-in must also set the **PshedFAErrorSourceControl** flag in the **FunctionalAreaMask** member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

The Windows kernel calls into the PSHED to disable an error source in response to an error source disable request by a WHEA management application. If a PSHED plug-in is registered to participate in error source control, the PSHED calls the PSHED plug-in's *DisableErrorSource* callback function to give the PSHED plug-in an opportunity to disable the error source. If the *DisableErrorSource* callback function returns STATUS_NOT_SUPPORTED, the PSHED will disable the error source. Otherwise, the PSHED will just return the return value that is returned by the *DisableErrorSource* callback function.

If the PSHED plug-in successfully disables the error source, the PSHED will update the WHEA_ERROR_SOURCE_DESCRIPTOR structure on behalf of the PSHED plug-in after the call to the PSHED plug-in's *DisableErrorSource* callback function returns. A PSHED plug-in's *DisableErrorSource* callback function should not modify the error source descriptor.

## -see-also

[EnableErrorSource](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_enable_error_source)

[PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin)

[SetErrorSourceInfo](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_set_error_source_info)

[**WHEA_ERROR_SOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor)

[**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet)
