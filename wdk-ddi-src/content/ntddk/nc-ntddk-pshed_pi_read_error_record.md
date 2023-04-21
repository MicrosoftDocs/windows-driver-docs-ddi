---
UID: NC:ntddk.PSHED_PI_READ_ERROR_RECORD
title: PSHED_PI_READ_ERROR_RECORD (ntddk.h)
description: A PSHED plug-in's ReadErrorRecord callback function reads an error record from the system's persistent data storage.
tech.root: whea
ms.date: 04/17/2023
keywords: ["PSHED_PI_READ_ERROR_RECORD callback function"]
ms.keywords: PSHED_PI_READ_ERROR_RECORD, PSHED_PI_READ_ERROR_RECORD callback, ReadErrorRecord, ReadErrorRecord callback function [WHEA Drivers and Applications], ntddk/ReadErrorRecord, whea.readerrorrecord, whearef_ec353a58-1ca7-4356-8651-52802d855582.xml
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
 - PSHED_PI_READ_ERROR_RECORD
 - ntddk/PSHED_PI_READ_ERROR_RECORD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ntddk.h
api_name:
 - PSHED_PI_READ_ERROR_RECORD
---

## -description

A PSHED plug-in's *ReadErrorRecord* callback function reads an error record from the system's persistent data storage.

## -parameters

### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the **Context** member of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure when the PSHED plug-in called the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED.

### -param Flags [in]

A bit-wise OR'ed combination of flags that affect the read operation. No flags are currently defined.

### -param ErrorRecordId [in]

The identifier of the error record to be read from the system's persistent data storage. If there is not an error record stored in the system's persistent data storage that matches this identifier, the *ReadErrorRecord* callback function must return STATUS_OBJECT_NOT_FOUND.

### -param NextErrorRecordId [out]

A pointer to a ULONGLONG-typed variable that receives the identifier of the next error record that is stored in the system's persistent data storage. If there are no other error records stored in the system's persistent data storage, the identifier for the error record that is currently being read should be returned in this parameter.

### -param RecordLength [in, out]

A pointer to a ULONG-typed variable that contains the size, in bytes, of the buffer pointed to by the *ErrorRecord* parameter. If the size of the buffer is large enough to contain the error record that is being read, the *ReadErrorRecord* callback function sets this variable to the size, in bytes, of the error record that is returned in the buffer. However, if the size of the buffer is too small to contain the error record that is being read, the *ReadErrorRecord* callback function sets this variable to the size, in bytes, that is required to contain the error record. In this situation the *ReadErrorRecord* callback function must return STATUS_BUFFER_TOO_SMALL.

### -param ErrorRecord [out]

A pointer to a buffer that receives the error record that is read from the system's persistent data storage.

## -returns

A PSHED plug-in's *ReadErrorRecord* callback function returns one of the following NTSTATUS codes:

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | The error record was successfully read from the system's persistent data storage. |
| **STATUS_OBJECT_NOT_FOUND** | There is no error record in the system's persistent data storage that matches the identifier specified in the *ErrorRecordId* parameter. |
| **STATUS_BUFFER_TOO_SMALL** | The size of the buffer is too small to contain the error record that is being read. |
| **STATUS_UNSUCCESSFUL** | An error occurred. |

## -remarks

A PSHED plug-in that participates in error record persistence sets the **Callbacks.WriteErrorRecord**, **Callbacks.ReadErrorRecord** and **Callbacks.ClearErrorRecord** members of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure to point to its [WriteErrorRecord](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_write_error_record), *ReadErrorRecord,* and [ClearErrorRecord](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_clear_error_record) callback functions when the plug-in calls the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED. The PSHED plug-in must also set the **PshedFAErrorRecordPersistence** flag in the **FunctionalAreaMask** member of the **WHEA_PSHED_PLUGIN_REGISTRATION_PACKET** structure.

The Windows kernel calls into the PSHED to read an error record from the system's persistent data storage after the system is restarted following a fatal or otherwise unrecoverable error condition. If a PSHED plug-in is registered to participate in error record persistence, the PSHED calls the PSHED plug-in's *ReadErrorRecord* callback function to perform the read operation. The mechanism that is used to read the error record from the system's persistent data storage is platform-specific.

## -see-also

[ClearErrorRecord](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_clear_error_record)

[PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin)

[**WHEA_ERROR_RECORD**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record)

[**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet)

[WriteErrorRecord](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_write_error_record)
