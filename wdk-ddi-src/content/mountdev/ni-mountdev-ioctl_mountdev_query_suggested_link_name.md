---
UID: NI:mountdev.IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME
title: IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME
author: windows-driver-content
description: Support for this IOCTL by the mount manager clients is optional.
old-location: storage\ioctl_mountdev_query_suggested_link_name.htm
tech.root: storage
ms.assetid: 4afd8c7a-b7b4-4a02-a270-d4e29f5329f9
ms.date: 03/29/2018
ms.keywords: IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME, IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME control, IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME control code [Storage Devices], k307_90b74e7c-57f6-4738-8a5e-d947c29c5aab.xml, mountdev/IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME, storage.ioctl_mountdev_query_suggested_link_name
ms.topic: ioctl
req.header: mountdev.h
req.include-header: Mountdev.h
req.target-type: Windows
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Mountdev.h
api_name:
-	IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME IOCTL

## -description

Support for this IOCTL by the mount manager clients is optional. Some mount manager clients are able to keep track of their drive letters across reboots of the system without the help of the mount manager. Such clients can send a suggested drive letter name to the mount manager in response to this IOCTL. The mount manager uses the suggested name if the mount manager's database does not already contain a persistent drive letter name for the client's volume. Otherwise, it ignores the suggestion and uses the drive letter name in its persistent name database.

Drive letter names must include the full path of the symbolic link in object namespace and must have the traditional MS-DOS syntax. For instance, drive letter "D" must be represented in this manner: "\DosDevices\D:". The alternative symbolic link path of "\??\D:" may not be used, nor may abbreviations of the symbolic link such as "D:". 

## -ioctlparameters

### -input-buffer

### -input-buffer-length

### -output-buffer

The client driver must place a variable-length structure of type [MOUNTDEV_SUGGESTED_LINK_NAME](ns-mountdev-_mountdev_suggested_link_name.md), defined in *moundev.h*, at the beginning of the buffer at **Irp-\>AssociatedIrp.SystemBuffer**. Starting at the address of the structure member *Name*, the client driver must insert the suggested persistent name.

### -output-buffer-length

**Parameters.DeviceIoControl.OutputBufferLength** in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer, which must be greater than or equal to **sizeof**(MOUNTDEV_SUGGESTED_LINK_NAME).

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the operation is successful, the **Information** field is set to the total number of bytes returned and the **Status** field is set to STATUS_SUCCESS.

If **OutputBufferLength** is less than **sizeof**(MOUNTDEV_SUGGESTED_LINK_NAME), the **Status** field is set to STATUS_INVALID_PARAMETER.

If **OutputBufferLength** is less than the total length of output data, the **Status** field is set to STATUS_BUFFER_OVERFLOW and the **Information** field is set to **sizeof**(MOUNTDEV_SUGGESTED_LINK_NAME).

## -remarks

The implementer of this function must not thread synchronize and must not make blocking and/or Interprocess Communication (IPC) function calls.

## -see-also

[MOUNTDEV_SUGGESTED_LINK_NAME](ns-mountdev-_mountdev_suggested_link_name.md)
