---
UID: NS:scsi.__unnamed_struct_27
title: RECEIVE_TOKEN_INFORMATION_HEADER (scsi.h)
description: The RECEIVE_TOKEN_INFORMATION_HEADER structure (scsi.h) contains information that describes the status of an offload data transfer operation.
tech.root: storage
ms.date: 09/19/2022
keywords: ["RECEIVE_TOKEN_INFORMATION_HEADER structure"]
ms.keywords: "*PRECEIVE_TOKEN_INFORMATION_HEADER, PRECEIVE_TOKEN_INFORMATION_HEADER, PRECEIVE_TOKEN_INFORMATION_HEADER structure pointer [Storage Devices], RECEIVE_TOKEN_INFORMATION_HEADER, RECEIVE_TOKEN_INFORMATION_HEADER structure [Storage Devices], SERVICE_ACTION_POPULATE_TOKEN, SERVICE_ACTION_WRITE_USING_TOKEN, TRANSFER_COUNT_UNITS_BYTES, TRANSFER_COUNT_UNITS_EXBIBYTES, TRANSFER_COUNT_UNITS_GIBIBYTES, TRANSFER_COUNT_UNITS_KIBIBYTES, TRANSFER_COUNT_UNITS_MEBIBYTES, TRANSFER_COUNT_UNITS_NUMBER_BLOCKS, TRANSFER_COUNT_UNITS_PEBIBYTES, TRANSFER_COUNT_UNITS_TEBIBYTES, scsi/PRECEIVE_TOKEN_INFORMATION_HEADER, scsi/RECEIVE_TOKEN_INFORMATION_HEADER, storage.receive_token_information_header"
req.header: scsi.h
req.include-header: Scsi.h, Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: 
targetos: Windows
req.typenames: RECEIVE_TOKEN_INFORMATION_HEADER, *PRECEIVE_TOKEN_INFORMATION_HEADER
f1_keywords:
 - PRECEIVE_TOKEN_INFORMATION_HEADER
 - scsi/PRECEIVE_TOKEN_INFORMATION_HEADER
 - RECEIVE_TOKEN_INFORMATION_HEADER
 - scsi/RECEIVE_TOKEN_INFORMATION_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - scsi.h
api_name:
 - PRECEIVE_TOKEN_INFORMATION_HEADER
 - RECEIVE_TOKEN_INFORMATION_HEADER
---

## -description

The **RECEIVE_TOKEN_INFORMATION_HEADER** structure contains information returned as status from an offload data transfer operation.

## -struct-fields

### -field AvailableData

The amount of data available in the **SenseData** array and any additional result information.

### -field ResponseToServiceAction

A response code indicating which command action the response is for. The service action codes are the following.

| Value | Meaning |
|--|--|
| **SERVICE_ACTION_POPULATE_TOKEN** | The response information is for a POPULATE TOKEN command. |
| **SERVICE_ACTION_WRITE_USING_TOKEN** | The response information is for a WRITE USING TOKEN command. |

### -field Reserved1

Reserved.

### -field OperationStatus

The current status of the copy operation. The status can be one of the following values.

| Value | Meaning |
|--|--|
| 0x01 | The operation completed successfully. |
| 0x02 | The operation completed unsuccessfully. |
| 0x04 | The operation completed successfully but the copy initiator should verify that all data was transferred. |
| 0x10 | The operation is in progress. Foreground or background operation state is unknown. |
| 0x11 | The operation is in progress in the foreground. |
| 0x12 | The operation is in progress in the background. |
| 0x60 | The operation was terminated. Possibly by an existing resource reservation. |

### -field Reserved2

Reserved.

### -field OperationCounter

The number of commands processed for the current copy operation.

### -field EstimatedStatusUpdateDelay

The recommended time, in milliseconds, to wait before sending the next RECEIVE COPY STATUS command for updated information about the current copy operation.

### -field CompletionStatus

SCSI status code for the copy command operation.

### -field SenseDataFieldLength

The length, in bytes, of the entire data area available for sense data. This value is always >=  **SenseDataLength**.

### -field SenseDataLength

The length, in bytes, of the data in **SenseData**.

### -field TransferCountUnits

The byte units applied to *TransferCount*. Each unit expansion is a exponent in base 2. The multiplier value of **TRANSFER_COUNT_UNITS_KIBIBYTES**, for example, is 1024 and not 1000. The defined units are the following.

| Value | Meaning |
|--|--|
| **TRANSFER_COUNT_UNITS_BYTES** | Transfer count is in bytes. |
| **TRANSFER_COUNT_UNITS_KIBIBYTES** | Transfer count is in kilobytes. |
| **TRANSFER_COUNT_UNITS_MEBIBYTES** | Transfer count is in megabytes. |
| **TRANSFER_COUNT_UNITS_GIBIBYTES** | Transfer count is in gigabytes. |
| **TRANSFER_COUNT_UNITS_TEBIBYTES** | Transfer count is in terabytes. |
| **TRANSFER_COUNT_UNITS_PEBIBYTES** | Transfer count is in petabytes. |
| **TRANSFER_COUNT_UNITS_EXBIBYTES** | Transfer count is in exabytes. |
| **TRANSFER_COUNT_UNITS_NUMBER_BLOCKS** | Transfer count is not an exponent, but in units of logical block length. |

### -field TransferCount

The length of data transferred in the operation. The unit type in **TransferCountUnits** is applied to this value to give the total byte count.

### -field SegmentsProcessed

The number of segments processed for the data transfer operation. Segments are copy length units used internally by a storage device's copy provider. On Windows systems, this value is reserved and applications must ignore this member.

### -field Reserved3

Reserved.

### -field SenseData

Sense data returned for the copy operation.

## -remarks

If **RECEIVE_TOKEN_INFORMATION_HEADER** is for a POPULATE TOKEN command operation, and the command completed successfully, a [**RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER**](/windows-hardware/drivers/ddi/minitape/ns-minitape-receive_token_information_response_header) structure will also be present after **SenseData** at an offset of **SenseDataFieldLength** from the beginning of the **SenseData** array. The **RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER** structure will contain the token created as a representation of data (ROD) for the range parameters sent with the command.

All multibyte values are in big endian format. Prior to evaluation, these values must be converted to match the endian format of the current platform.

## -see-also

[**RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER**](/windows-hardware/drivers/ddi/minitape/ns-minitape-receive_token_information_response_header)
