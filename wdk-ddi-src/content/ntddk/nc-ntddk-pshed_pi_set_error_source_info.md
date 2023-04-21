---
UID: NC:ntddk.PSHED_PI_SET_ERROR_SOURCE_INFO
title: PSHED_PI_SET_ERROR_SOURCE_INFO (ntddk.h)
description: A PSHED plug-in's SetErrorSourceInfo callback function configures an error source.
tech.root: whea
ms.date: 04/17/2023
keywords: ["PSHED_PI_SET_ERROR_SOURCE_INFO callback function"]
ms.keywords: PSHED_PI_SET_ERROR_SOURCE_INFO, PSHED_PI_SET_ERROR_SOURCE_INFO callback, SetErrorSourceInfo, SetErrorSourceInfo callback function [WHEA Drivers and Applications], ntddk/SetErrorSourceInfo, whea.seterrorsourceinfo, whearef_49924aa5-519d-4e23-95c5-a52264713258.xml
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
 - PSHED_PI_SET_ERROR_SOURCE_INFO
 - ntddk/PSHED_PI_SET_ERROR_SOURCE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ntddk.h
api_name:
 - PSHED_PI_SET_ERROR_SOURCE_INFO
---

## -description

A PSHED plug-in's *SetErrorSourceInfo* callback function configures an error source.

## -parameters

### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the **Context** member of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure when the PSHED plug-in called the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED.

### -param ErrorSource [in]

A pointer to a [**WHEA_ERROR_SOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor) structure that describes the error source that is being configured.

## -returns

A PSHED plug-in's *SetErrorSourceInfo* callback function returns one of the following NTSTATUS codes:

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | The error source was successfully configured. |
| **STATUS_NOT_SUPPORTED** | The PSHED plug-in does not support configuration of the specified error source. |
| **STATUS_UNSUCCESSFUL** | An error occurred. |

## -remarks

A PSHED plug-in that participates in error source control sets the **Callbacks.SetErrorSourceInfo**, **Callbacks.EnableErrorSource**, and **Callbacks.DisableErrorSource** members of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure to point to its *SetErrorSourceInfo*, [EnableErrorSource](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_enable_error_source), and [DisableErrorSource](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_disable_error_source) callback functions when the plug-in calls the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED. The PSHED plug-in must also set the **PshedFAErrorSourceControl** flag in the **FunctionalAreaMask** member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

The Windows kernel calls into the PSHED to configure an error source in response to an error source configuration request by a WHEA management application. If a PSHED plug-in is registered to participate in error source control, the PSHED calls the PSHED plug-in's *SetErrorSourceInfo* callback function to give the PSHED plug-in an opportunity to perform the error source configuration operation. The error source configuration data is included in the [**WHEA_ERROR_SOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor) structure that is pointed to by the *ErrorSource* parameter.

If the PSHED plug-in does not support configuration of the specified error source, the *SetErrorSourceInfo* callback function returns STATUS_NOT_SUPPORTED. In this situation, the PSHED performs the requested error source configuration operation.

If the PSHED plug-in's supports configuration of the specified error source, the *SetErrorSourceInfo* callback function should save the error source's configuration data in the registry, in the system's BIOS tables, or in some other form of nonvolatile data storage that is available to the error source. The specific form of nonvolatile data storage that is used by an error source for storing the error source's configuration data is implementation-specific. The *SetErrorSourceInfo* callback function should apply the configuration data to the error source in such a way that the configuration changes become effective the next time that the system is restarted. When the system is restarted, the PSHED plug-in should report the new error source configuration data for the error source to the operating system during error source discovery.

## -see-also

[DisableErrorSource](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_disable_error_source)

[EnableErrorSource](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_enable_error_source)

[PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin)

[**WHEA_ERROR_SOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor)

[**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet)
