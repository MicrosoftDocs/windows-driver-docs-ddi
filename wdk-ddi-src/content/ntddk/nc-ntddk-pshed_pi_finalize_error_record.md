---
UID: NC:ntddk.PSHED_PI_FINALIZE_ERROR_RECORD
title: PSHED_PI_FINALIZE_ERROR_RECORD (ntddk.h)
description: A PSHED plug-in's FinalizeErrorRecord callback function adds supplementary error record sections to an error record that more fully describe the error condition.
tech.root: whea
ms.date: 04/17/2023
keywords: ["PSHED_PI_FINALIZE_ERROR_RECORD callback function"]
ms.keywords: FinalizeErrorRecord, FinalizeErrorRecord callback function [WHEA Drivers and Applications], PSHED_PI_FINALIZE_ERROR_RECORD, PSHED_PI_FINALIZE_ERROR_RECORD callback, ntddk/FinalizeErrorRecord, whea.finalizeerrorrecord, whearef_fac1a23e-6b56-4b04-8930-e5f12f5c84a8.xml
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
req.irql: IRQL >= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PSHED_PI_FINALIZE_ERROR_RECORD
 - ntddk/PSHED_PI_FINALIZE_ERROR_RECORD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ntddk.h
api_name:
 - PSHED_PI_FINALIZE_ERROR_RECORD
---

## -description

A PSHED plug-in's *FinalizeErrorRecord* callback function adds supplementary error record sections to an error record that more fully describe the error condition.

## -parameters

### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the **Context** member of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure when the PSHED plug-in called the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED.

### -param ErrorSource [in]

A pointer to a [**WHEA_ERROR_SOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor) structure that describes the error source that reported the hardware error.

### -param BufferLength [in]

The size, in bytes, of the buffer pointed to by the *ErrorRecord* parameter.

### -param ErrorRecord [in, out]

A pointer to a [**WHEA_ERROR_RECORD**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record) structure that describes the error record that is being updated with supplementary error record sections.

## -returns

A PSHED plug-in's *FinalizeErrorRecord* callback function returns one of the following NTSTATUS codes:

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | The error record was successfully updated with any supplementary error record sections. |
| **STATUS_BUFFER_TOO_SMALL** | The size of the buffer pointed to by the *ErrorRecord* parameter as specified by the *BufferLength* parameter is too small to contain the error record if it is updated with the supplementary error record sections. |
| **STATUS_NOT_SUPPORTED** | The PSHED plug-in does not support the specified error source. |
| **STATUS_UNSUCCESSFUL** | An error occurred. |

## -remarks

A PSHED plug-in that participates in error information retrieval sets the **Callbacks.RetrieveErrorInfo**, **Callbacks.FinalizeErrorRecord**, and **Callbacks.ClearErrorStatus** members of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure to point to its [RetrieveErrorInfo](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_retrieve_error_info), *FinalizeErrorRecord*, and [ClearErrorStatus](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_clear_error_status) callback functions when the plug-in calls the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED. The PSHED plug-in must also set the **PshedFAErrorInfoRetrieval** flag in the **FunctionalAreaMask** member of the **WHEA_PSHED_PLUGIN_REGISTRATION_PACKET** structure.

The Windows kernel calls into the PSHED so that it can add supplementary error record sections to an error record. If a PSHED plug-in is registered to participate in error information retrieval, the PSHED calls the PSHED plug-in's *FinalizeErrorRecord* callback function so that the PSHED plug-in can add any additional error record sections to the error record that more fully describe the error condition.

A PSHED plug-in must ensure that it does not add supplementary error record sections beyond the end of the error record. The amount of memory that the Windows kernel allocates for a buffer to contain a particular error record is calculated from the **MaxRawDataLength** and **MaxSectionsPerRecord** members of the [**WHEA_ERROR_SOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor) structure that describes the error source that reported the hardware error. If a PSHED plug-in requires additional buffer space to contain the supplementary error record sections that it adds to the error record, it must participate in error source discovery and increase the value in the **MaxSectionsPerRecord** member of the **WHEA_ERROR_SOURCE_DESCRIPTOR** structure for each error source as appropriate to account for any supplementary error record sections.

## -see-also

[ClearErrorStatus](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_clear_error_status)

[PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin)

[RetrieveErrorInfo](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_retrieve_error_info)

[**WHEA_ERROR_RECORD**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record)

[**WHEA_ERROR_SOURCE_DESCRIPTOR**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_source_descriptor)

[**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet)
