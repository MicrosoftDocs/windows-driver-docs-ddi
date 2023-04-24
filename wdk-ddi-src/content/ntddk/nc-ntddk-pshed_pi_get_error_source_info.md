---
UID: NC:ntddk.PSHED_PI_GET_ERROR_SOURCE_INFO
title: PSHED_PI_GET_ERROR_SOURCE_INFO (ntddk.h)
description: A PSHED plug-in's GetErrorSourceInfo callback function returns an error source descriptor structure that represents a particular error source that is implemented by the hardware platform.
tech.root: whea
ms.date: 04/17/2023
keywords: ["PSHED_PI_GET_ERROR_SOURCE_INFO callback function"]
ms.keywords: GetErrorSourceInfo, GetErrorSourceInfo callback function [WHEA Drivers and Applications], PSHED_PI_GET_ERROR_SOURCE_INFO, PSHED_PI_GET_ERROR_SOURCE_INFO callback, ntddk/GetErrorSourceInfo, whea.geterrorsourceinfo, whearef_977e9d78-23ec-408f-ba18-a4a96f9a8e62.xml
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
 - PSHED_PI_GET_ERROR_SOURCE_INFO
 - ntddk/PSHED_PI_GET_ERROR_SOURCE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ntddk.h
api_name:
 - PSHED_PI_GET_ERROR_SOURCE_INFO
---

## -description

A PSHED plug-in's *GetErrorSourceInfo* callback function returns an error source descriptor structure that represents a particular error source that is implemented by the hardware platform.

## -parameters

### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the **Context** member of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure when the PSHED plug-in called the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED.

### -param ErrorSource [in, out]

A pointer to a [**WHEA_ERROR_SOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor) structure that represents a particular error source that is implemented by the hardware platform.

## -returns

A PSHED plug-in's *GetErrorSourceInfo* callback function returns one of the following NTSTATUS codes:

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | The error source information was successfully updated. |
| **STATUS_UNSUCCESSFUL** | An error occurred. |

## -remarks

A PSHED plug-in that participates in error source discovery sets the **Callbacks.GetAllErrorSources** member and, optionally, the **Callbacks.GetErrorSourceInfo** member of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure to point to its [GetAllErrorSources](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_get_all_error_sources) and *GetErrorSourceInfo* callback functions when the plug-in calls the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED. The PSHED plug-in must also set the **PshedFADiscovery** flag in the **FunctionalAreaMask** member of the **WHEA_PSHED_PLUGIN_REGISTRATION_PACKET** structure.

The Windows kernel calls into the PSHED to obtain additional details about a particular error source. This occurs when a new error source is added to the system by a bus driver. For example, when the PCI driver discovers a PCI Express (PCIe) device that is capable of reporting PCIe errors, it reports the error source to the operating system.

If a PSHED plug-in is registered to participate in error source discovery and it has implemented a *GetErrorSourceInfo* callback function, after the PSHED has updated the error source descriptor structure with the information that it has collected about the error source, the PSHED calls the PSHED plug-in's *GetErrorSourceInfo* callback function so that the PSHED plug-in can provide additional details about the error source. The *GetErrorSourceInfo* callback function updates the contents of the error source descriptor structure so that it accurately represents the error source as it is implemented by the hardware platform.

## -see-also

[GetAllErrorSources](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_get_all_error_sources)

[PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin)

[**WHEA_ERROR_SOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor)

[**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet)
