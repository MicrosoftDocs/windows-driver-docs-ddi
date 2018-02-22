---
UID: NS:ntddstor._STORAGE_PROTOCOL_COMMAND
title: "_STORAGE_PROTOCOL_COMMAND"
author: windows-driver-content
description: This structure is used as an input buffer when using the pass-through mechanism to issue a vendor-specific command to a storage device (via IOCTL_STORAGE_PROTOCOL_COMMAND).
old-location: storage\storage_protocol_command.htm
old-project: storage
ms.assetid: 0B7FC33E-A417-48E4-99CC-D1FFC340A405
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: STORAGE_PROTOCOL_COMMAND, PSTORAGE_PROTOCOL_COMMAND structure pointer [Storage Devices], STORAGE_PROTOCOL_COMMAND structure [Storage Devices], _STORAGE_PROTOCOL_COMMAND, ntddstor/PSTORAGE_PROTOCOL_COMMAND, *PSTORAGE_PROTOCOL_COMMAND, storage.storage_protocol_command, PSTORAGE_PROTOCOL_COMMAND, ntddstor/STORAGE_PROTOCOL_COMMAND
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddstor.h
apiname:
-	STORAGE_PROTOCOL_COMMAND
product: Windows
targetos: Windows
req.typenames: STORAGE_PROTOCOL_COMMAND, *PSTORAGE_PROTOCOL_COMMAND
---

# _STORAGE_PROTOCOL_COMMAND structure


## -description


This structure is used as an input buffer when using the pass-through mechanism to issue  a vendor-specific command to a storage device (via <a href="..\ntddstor\ni-ntddstor-ioctl_storage_protocol_command.md">IOCTL_STORAGE_PROTOCOL_COMMAND</a>).


## -syntax


````
typedef struct _STORAGE_PROTOCOL_COMMAND {
  ULONG                                        Version;
  ULONG                                        Length;
  STORAGE_PROTOCOL_TYPE                        ProtocolType;
  ULONG                                        Flags;
  ULONG                                        ReturnStatus;
  ULONG                                        ErrorCode;
  ULONG                                        CommandLength;
  ULONG                                        ErrorInfoLength;
  ULONG                                        DataToDeviceTransferLength;
  ULONG                                        DataFromDeviceTransferLength;
  ULONG                                        TimeOutValue;
  ULONG                                        ErrorInfoOffset;
  ULONG                                        DataToDeviceBufferOffset;
  ULONG                                        DataFromDeviceBufferOffset;
  ULONG                                        CommandSpecific;
  ULONG                                        Reserved0;
  ULONG                                        FixedProtocolReturnData;
  ULONG                                        Reserved1[3];
  _Field_size_bytes_full_(CommandLength) UCHAR Command[ANYSIZE_ARRAY];
} STORAGE_PROTOCOL_COMMAND, *PSTORAGE_PROTOCOL_COMMAND;
````


## -struct-fields




### -field Version

The version of this structure. This should be set to <b>STORAGE_PROTOCOL_STRUCTURE_VERSION</b>.


### -field Length

The size of this structure. This should be set to sizeof(<b>STORAGE_PROTOCOL_COMMAND</b>).


### -field ProtocolType

The protocol type.


### -field Flags

Flags set for this request. The following are valid flags.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td><b>STORAGE_PROTOCOL_COMMAND_FLAG_ADAPTER_REQUEST</b></td>
<td>This flag indicates the request to target an adapter instead of device.</td>
</tr>
</table>
 


### -field ReturnStatus

The status of the request made to the storage device. In Windows 10, possible values include: 

<table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<tr>
<td><b>STORAGE_PROTOCOL_STATUS_PENDING</b></td>
<td>The request is pending.</td>
</tr>
<tr>
<td><b>STORAGE_PROTOCOL_STATUS_SUCCESS</b></td>
<td>The request has completed successfully.</td>
</tr>
<tr>
<td><b>STORAGE_PROTOCOL_STATUS_ERROR</b></td>
<td>The request has encountered an error.</td>
</tr>
<tr>
<td><b>STORAGE_PROTOCOL_STATUS_INVALID_REQUEST</b></td>
<td>The request is not valid.</td>
</tr>
<tr>
<td><b>STORAGE_PROTOCOL_STATUS_NO_DEVICE</b></td>
<td>A device is not available to make a request to.</td>
</tr>
<tr>
<td><b>STORAGE_PROTOCOL_STATUS_BUSY</b></td>
<td>The device is busy acting on the request.</td>
</tr>
<tr>
<td><b>STORAGE_PROTOCOL_STATUS_DATA_OVERRUN</b></td>
<td>The device encountered a data overrun while acting on the request.</td>
</tr>
<tr>
<td><b>STORAGE_PROTOCOL_STATUS_INSUFFICIENT_RESOURCES</b></td>
<td>The device cannot complete the request due to insufficient resources.</td>
</tr>
<tr>
<td><b>STORAGE_PROTOCOL_STATUS_NOT_SUPPORTED</b></td>
<td>The request is not supported.</td>
</tr>
</table>
 


### -field ErrorCode

The error code for this request. This is optionally set.


### -field CommandLength

The length of the command. A non-zero value must be set by the caller.


### -field ErrorInfoLength

The length of the error buffer. This is optionally set and can be set to 0.


### -field DataToDeviceTransferLength

The size of the buffer that is to be transferred to the device. This is only used with a WRITE request.


### -field DataFromDeviceTransferLength

The size of the buffer this is to be transferred from the device. This is only used with a READ request.


### -field TimeOutValue

How long to wait for the device until timing out. This is set in units of seconds.


### -field ErrorInfoOffset

The offset of the error buffer. This must be pointer-aligned.


### -field DataToDeviceBufferOffset

The offset of the buffer that is to be transferred to the device. This must be pointer-aligned and is only used with a WRITE request.


### -field DataFromDeviceBufferOffset

The offset of the buffer that is to be transferred from the device. This must be pointer-aligned and is only used with a READ request.


### -field CommandSpecific

Command-specific data passed along with the command. This depends on the command from the driver, and is optionally set.


### -field Reserved0

Reserved for future use.


### -field FixedProtocolReturnData

The return data. This is optionally set. Some protocols such as NVMe, may return a small amount of data (DWORD0 from completion queue entry) without the need of a separate device data transfer.


### -field Reserved1

Reserved for future use.


### -field Command

 




#### - Command[ANYSIZE_ARRAY]

The vendor-specific command that is to be passed-through to the device. 


## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_protocol_command.md">IOCTL_STORAGE_PROTOCOL_COMMAND</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_PROTOCOL_COMMAND structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

