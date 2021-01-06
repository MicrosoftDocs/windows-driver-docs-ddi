---
UID: NS:ntddstor._STORAGE_PROTOCOL_COMMAND
title: _STORAGE_PROTOCOL_COMMAND (ntddstor.h)
description: This structure is used as an input buffer when using the pass-through mechanism to issue a vendor-specific command to a storage device (via IOCTL_STORAGE_PROTOCOL_COMMAND).
old-location: storage\storage_protocol_command.htm
tech.root: storage
ms.date: 06/11/2019
keywords: ["STORAGE_PROTOCOL_COMMAND structure"]
ms.keywords: "*PSTORAGE_PROTOCOL_COMMAND, PSTORAGE_PROTOCOL_COMMAND, PSTORAGE_PROTOCOL_COMMAND structure pointer [Storage Devices], STORAGE_PROTOCOL_COMMAND, STORAGE_PROTOCOL_COMMAND structure [Storage Devices], _STORAGE_PROTOCOL_COMMAND, ntddstor/PSTORAGE_PROTOCOL_COMMAND, ntddstor/STORAGE_PROTOCOL_COMMAND, storage.storage_protocol_command"
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.typenames: STORAGE_PROTOCOL_COMMAND, *PSTORAGE_PROTOCOL_COMMAND
f1_keywords:
 - _STORAGE_PROTOCOL_COMMAND
 - ntddstor/_STORAGE_PROTOCOL_COMMAND
 - PSTORAGE_PROTOCOL_COMMAND
 - ntddstor/PSTORAGE_PROTOCOL_COMMAND
 - STORAGE_PROTOCOL_COMMAND
 - ntddstor/STORAGE_PROTOCOL_COMMAND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - STORAGE_PROTOCOL_COMMAND
---

# _STORAGE_PROTOCOL_COMMAND structure


## -description

This structure is used with the [IOCTL_STORAGE_PROTOCOL_COMMAND](./ni-ntddstor-ioctl_storage_protocol_command.md) pass-through mechanism that issues a vendor-specific protocol command to a storage device.

## -struct-fields

### -field Version

The version of this structure. Set this to be **STORAGE_PROTOCOL_STRUCTURE_VERSION**.

### -field Length

The size of this structure. Set this to sizeof(**STORAGE_PROTOCOL_COMMAND**).

### -field ProtocolType

The protocol type.

### -field Flags

Flags set for this request. The following are valid flags.

| Flag | Description |
| ---- | ----------- |
| **STORAGE_PROTOCOL_COMMAND_FLAG_ADAPTER_REQUEST** | This flag indicates the request to target an adapter instead of device. |

### -field ReturnStatus

The status of the request made to the storage device. In Windows 10, possible values that can be returned include:

| Status value | Description |
| ------------ | ----------- |
| **STORAGE_PROTOCOL_STATUS_PENDING**                | The request is pending. |
| **STORAGE_PROTOCOL_STATUS_SUCCESS**                | The request has completed successfully. |
| **STORAGE_PROTOCOL_STATUS_ERROR**                  | The request has encountered an error. |
| **STORAGE_PROTOCOL_STATUS_INVALID_REQUEST**        | The request is not valid. |
| **STORAGE_PROTOCOL_STATUS_NO_DEVICE**              | A device is not available to make a request to. |
| **STORAGE_PROTOCOL_STATUS_BUSY**                   | The device is busy acting on the request. |
| **STORAGE_PROTOCOL_STATUS_DATA_OVERRUN**           | The device encountered a data overrun while acting on the request. |
| **STORAGE_PROTOCOL_STATUS_INSUFFICIENT_RESOURCES** | The device cannot complete the request due to insufficient resources. |
| **STORAGE_PROTOCOL_STATUS_NOT_SUPPORTED**          | The request is not supported. |

### -field ErrorCode

The bus-specific protocol error code to return for this request. This is optionally set.

### -field CommandLength

The length of the command, in bytes. The caller must set this to a non-zero value.

### -field ErrorInfoLength

The length of the **ErrorCode** buffer, in bytes. This is optionally set and can be set to 0.

### -field DataToDeviceTransferLength

The size of the buffer that is to be transferred to the device.

### -field DataFromDeviceTransferLength

The size of the buffer this is to be transferred from the device.

### -field TimeOutValue

Specifies how long to wait for the device until timing out. This is set in units of seconds.

### -field ErrorInfoOffset

The offset of the **ErrorCode** buffer. This must be pointer-aligned.

### -field DataToDeviceBufferOffset

The offset of the buffer that is to be transferred to the device. This must be pointer-aligned and is only used with a WRITE request.

### -field DataFromDeviceBufferOffset

The offset of the buffer that is to be transferred from the device. This must be pointer-aligned and is only used with a READ request.

### -field CommandSpecific

Additional command-specific data passed along with **Command**. This depends on the command from the driver, and is optionally set.

### -field Reserved0

Reserved for future use.

### -field FixedProtocolReturnData

The return data. This is optionally set. Some protocols such as NVMe, may return a small amount of data (DWORD0 from completion queue entry) without the need of a separate device data transfer.

### -field Reserved1

Reserved for future use.

### -field Command

The vendor-specific command that is to be passed-through to the device.

## -see-also

[IOCTL_STORAGE_PROTOCOL_COMMAND](./ni-ntddstor-ioctl_storage_protocol_command.md)
