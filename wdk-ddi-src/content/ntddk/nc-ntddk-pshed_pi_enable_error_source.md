---
UID: NC:ntddk.PSHED_PI_ENABLE_ERROR_SOURCE
title: PSHED_PI_ENABLE_ERROR_SOURCE (ntddk.h)
description: A PSHED plug-in's EnableErrorSource callback function enables an error source.
tech.root: whea
ms.date: 04/17/2023
keywords: ["PSHED_PI_ENABLE_ERROR_SOURCE callback function"]
ms.keywords: EnableErrorSource, EnableErrorSource callback function [WHEA Drivers and Applications], PSHED_PI_ENABLE_ERROR_SOURCE, PSHED_PI_ENABLE_ERROR_SOURCE callback, ntddk/EnableErrorSource, whea.enableerrorsource, whearef_d2fcd602-03f5-466c-bd90-abd81f15ec38.xml
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
 - PSHED_PI_ENABLE_ERROR_SOURCE
 - ntddk/PSHED_PI_ENABLE_ERROR_SOURCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ntddk.h
api_name:
 - PSHED_PI_ENABLE_ERROR_SOURCE
---

## -description

A PSHED plug-in's *EnableErrorSource* callback function enables an error source.

## -parameters

### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the **Context** member of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure when the PSHED plug-in called the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED.

### -param ErrorSource [in]

A pointer to a [**WHEA_ERROR_SOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor) structure that describes the error source that is being enabled.

## -returns

A PSHED plug-in's *EnableErrorSource* callback function returns one of the following NTSTATUS codes:

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | The error source was successfully enabled. |
| **STATUS_NOT_SUPPORTED** | The PSHED plug-in does not support enabling the specified error source. |
| **STATUS_UNSUCCESSFUL** | An error occurred. |

## -remarks

A PSHED plug-in that participates in error source control sets the **Callbacks.SetErrorSourceInfo**, **Callbacks.EnableErrorSource**, and **Callbacks.DisableErrorSource** members of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure to point to its [SetErrorSourceInfo](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_set_error_source_info), *EnableErrorSource*, and [DisableErrorSource](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_disable_error_source) callback functions when the plug-in calls the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED. The PSHED plug-in must also set the **PshedFAErrorSourceControl** flag in the **FunctionalAreaMask** member of the **WHEA_PSHED_PLUGIN_REGISTRATION_PACKET** structure.

The Windows kernel calls into the PSHED to enable each of the error sources that were reported during error source discovery. The Windows kernel also calls into the PSHED to enable an error source in response to an error source enable request by a WHEA management application. If a PSHED plug-in is registered to participate in error source control, the PSHED calls the PSHED plug-in's *EnableErrorSource* callback function to give the PSHED plug-in an opportunity to enable the error source. If the *EnableErrorSource* callback function returns STATUS_NOT_SUPPORTED, the PSHED will enable the error source. Otherwise, the PSHED will just return the return value that is returned by the *EnableErrorSource* callback function.

If the PSHED plug-in successfully enables the error source, the PSHED will update the WHEA_ERROR_SOURCE_DESCRIPTOR structure on behalf of the PSHED plug-in after the call to the PSHED plug-in's *EnableErrorSource* callback function returns. A PSHED plug-in's *EnableErrorSource* callback function should not modify the error source descriptor.

## -see-also

[DisableErrorSource](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_disable_error_source)

[PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin)

[SetErrorSourceInfo](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_set_error_source_info)

[**WHEA_ERROR_SOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor)

[**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet)
