---
UID: NC:ntddk.PSHED_PI_WRITE_ERROR_RECORD
title: PSHED_PI_WRITE_ERROR_RECORD (ntddk.h)
description: A PSHED plug-in's WriteErrorRecord callback function writes an error record to the system's persistent data storage.
tech.root: whea
ms.date: 04/17/2023
keywords: ["PSHED_PI_WRITE_ERROR_RECORD callback function"]
ms.keywords: PSHED_PI_WRITE_ERROR_RECORD, PSHED_PI_WRITE_ERROR_RECORD callback, WriteErrorRecord, WriteErrorRecord callback function [WHEA Drivers and Applications], ntddk/WriteErrorRecord, whea.writeerrorrecord, whearef_3a405d7d-3427-4c22-919e-7cbab5ea4f19.xml
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
 - PSHED_PI_WRITE_ERROR_RECORD
 - ntddk/PSHED_PI_WRITE_ERROR_RECORD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ntddk.h
api_name:
 - PSHED_PI_WRITE_ERROR_RECORD
---

## -description

A PSHED plug-in's *WriteErrorRecord* callback function writes an error record to the system's persistent data storage.

## -parameters

### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the **Context** member of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure when the PSHED plug-in called the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED.

### -param Flags [in]

A bit-wise OR'ed combination of flags that affect the write operation. A possible flag is:

#### WHEA_WRITE_FLAG_DUMMY

The write operation is a dummy write operation. No data is to be written to the system's persistent data storage.

### -param RecordLength [in]

The size, in bytes, of the error record pointed to by the *ErrorRecord* parameter.

### -param ErrorRecord [in]

A pointer to a [**WHEA_ERROR_RECORD**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record) structure that describes the error record that is being written to the system's persistent data storage.

## -returns

A PSHED plug-in's *WriteErrorRecord* callback function returns one of the following NTSTATUS codes:

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | The error record was successfully written to the system's persistent data storage. |
| **STATUS_UNSUCCESSFUL** | An error occurred. |

## -remarks

A PSHED plug-in that participates in error record persistence sets the **Callbacks.WriteErrorRecord**, **Callbacks.ReadErrorRecord** and **Callbacks.ClearErrorRecord** members of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure to point to its *WriteErrorRecord*, [ReadErrorRecord](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_read_error_record), and [ClearErrorRecord](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_clear_error_record) callback functions when the plug-in calls the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED. The PSHED plug-in must also set the **PshedFAErrorRecordPersistence** flag in the **FunctionalAreaMask** member of the **WHEA_PSHED_PLUGIN_REGISTRATION_PACKET** structure.

The Windows kernel calls into the PSHED to write an error record to the system's persistent data storage whenever a fatal or otherwise unrecoverable error condition exists so that the error record is preserved while the system is restarted. If a PSHED plug-in is registered to participate in error record persistence, the PSHED calls the PSHED plug-in's *WriteErrorRecord* callback function to perform the write operation. The mechanism that is used to write the error record to the system's persistent data storage is platform-specific.

## -see-also

[ClearErrorRecord](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_clear_error_record)

[PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin)

[ReadErrorRecord](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_read_error_record)

[**WHEA_ERROR_RECORD**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record)

[**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet)
