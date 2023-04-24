---
UID: NC:ntddk.PSHED_PI_CLEAR_ERROR_RECORD
title: PSHED_PI_CLEAR_ERROR_RECORD (ntddk.h)
description: A PSHED plug-in's ClearErrorRecord callback function clears the specified error record from the system's persistent data storage.
tech.root: whea
ms.date: 04/17/2023
keywords: ["PSHED_PI_CLEAR_ERROR_RECORD callback function"]
ms.keywords: ClearErrorRecord, ClearErrorRecord callback function [WHEA Drivers and Applications], PSHED_PI_CLEAR_ERROR_RECORD, PSHED_PI_CLEAR_ERROR_RECORD callback, ntddk/ClearErrorRecord, whea.clearerrorrecord, whearef_1644b60c-c232-4cca-805b-d6a061425f61.xml
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
 - PSHED_PI_CLEAR_ERROR_RECORD
 - ntddk/PSHED_PI_CLEAR_ERROR_RECORD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ntddk.h
api_name:
 - PSHED_PI_CLEAR_ERROR_RECORD
---

## -description

A PSHED plug-in's *ClearErrorRecord* callback function clears the specified error record from the system's persistent data storage.

## -parameters

### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the **Context** member of the [WHEA_PSHED_PLUGIN_REGISTRATION_PACKET](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure when the PSHED plug-in called the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED.

### -param Flags [in]

A bit-wise OR'ed combination of flags that affect the clear operation. No flags are currently defined.

### -param ErrorRecordId [in]

The identifier of the error record that is being cleared from the system's persistent data storage. This identifier should be compared to the **Header.RecordId** member of each [WHEA_ERROR_RECORD](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record) structure that has been written to the system's persistent data storage to identify the error record to be cleared.

## -returns

A PSHED plug-in's *ClearErrorRecord* callback function returns one of the following NTSTATUS codes:

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | The error record was successfully cleared from the system's persistent data storage. |
| **STATUS_UNSUCCESSFUL** | An error occurred. |

## -remarks

A PSHED plug-in that participates in error record persistence sets the **Callbacks.WriteErrorRecord**, **Callbacks.ReadErrorRecord** and **Callbacks.ClearErrorRecord** members of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure to point to its [WriteErrorRecord](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_write_error_record), [ReadErrorRecord](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_read_error_record), and *ClearErrorRecord* callback functions when the plug-in calls the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED. The PSHED plug-in must also set the **PshedFAErrorRecordPersistence** flag in the **FunctionalAreaMask** member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

The Windows kernel calls into the PSHED to clear an error record from the system's persistent data storage. If a PSHED plug-in is registered to participate in error record persistence, the PSHED calls the PSHED plug-in's *ClearErrorRecord* callback function to perform the clear operation. The mechanism that is used to clear the error record from the system's persistent data storage is platform-specific.

## -see-also

[PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin)

[ReadErrorRecord](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_read_error_record)

[**WHEA_ERROR_RECORD**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record)

[**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet)

[WriteErrorRecord](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_write_error_record)
