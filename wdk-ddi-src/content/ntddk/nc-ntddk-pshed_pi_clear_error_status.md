---
UID: NC:ntddk.PSHED_PI_CLEAR_ERROR_STATUS
title: PSHED_PI_CLEAR_ERROR_STATUS (ntddk.h)
description: A PSHED plug-in's ClearErrorStatus callback function clears any platform-specific error status registers for a corrected hardware error condition.
tech.root: whea
ms.date: 04/17/2023
keywords: ["PSHED_PI_CLEAR_ERROR_STATUS callback function"]
ms.keywords: ClearErrorStatus, ClearErrorStatus callback function [WHEA Drivers and Applications], PSHED_PI_CLEAR_ERROR_STATUS, PSHED_PI_CLEAR_ERROR_STATUS callback, ntddk/ClearErrorStatus, whea.clearerrorstatus, whearef_022b6321-f051-4d35-ad0c-e6528d03a411.xml
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
 - PSHED_PI_CLEAR_ERROR_STATUS
 - ntddk/PSHED_PI_CLEAR_ERROR_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ntddk.h
api_name:
 - PSHED_PI_CLEAR_ERROR_STATUS
---

## -description

A PSHED plug-in's *ClearErrorStatus* callback function clears any platform-specific error status registers for a corrected hardware error condition.

## -parameters

### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the **Context** member of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure when the PSHED plug-in called the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED.

### -param ErrorSource [in]

A pointer to a [**WHEA_ERROR_SOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor) structure that describes the error source that reported the hardware error.

### -param BufferLength [in]

The size, in bytes, of the buffer pointed to by the *ErrorRecord* parameter.

### -param ErrorRecord [in]

A pointer to a [**WHEA_ERROR_RECORD**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record) structure that describes an error record. The error record describes the corrected hardware error condition for which the platform-specific error status registers are being cleared.

## -returns

A PSHED plug-in's *ClearErrorStatus* callback function returns one of the following NTSTATUS codes:

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | The platform-specific error status registers for the corrected hardware error condition were successfully cleared. |
| **STATUS_NOT_SUPPORTED** | The PSHED plug-in does not support the specified error source. |
| **STATUS_UNSUCCESSFUL** | An error occurred. |

## -remarks

A PSHED plug-in that participates in error information retrieval sets the **Callbacks.RetrieveErrorInfo**, **Callbacks.FinalizeErrorRecord**, and **Callbacks.ClearErrorStatus** members of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure to point to its [RetrieveErrorInfo](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_retrieve_error_info), [FinalizeErrorRecord](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_finalize_error_record), and *ClearErrorStatus* callback functions when the plug-in calls the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED. The PSHED plug-in must also set the **PshedFAErrorInfoRetrieval** flag in the **FunctionalAreaMask** member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

For corrected hardware error conditions, the Windows kernel calls into the PSHED to clear the error source's error status registers as the final step of processing the error. If a PSHED plug-in is registered to participate in error information retrieval, the PSHED calls the PSHED plug-in's *ClearErrorStatus* callback function so that the PSHED plug-in can clear any additional platform-specific error status registers.

## -see-also

[FinalizeErrorRecord](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_finalize_error_record)

[PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin)

[RetrieveErrorInfo](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_retrieve_error_info)

[**WHEA_ERROR_RECORD**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record)

[**WHEA_ERROR_SOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor)

[**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet)
