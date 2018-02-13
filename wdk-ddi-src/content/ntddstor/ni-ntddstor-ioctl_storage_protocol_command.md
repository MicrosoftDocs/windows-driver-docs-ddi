---
UID: NI:ntddstor.IOCTL_STORAGE_PROTOCOL_COMMAND
title: IOCTL_STORAGE_PROTOCOL_COMMAND
author: windows-driver-content
description: A driver can use IOCTL_STORAGE_PROTOCOL_COMMAND to pass vendor-specific commands to a storage device.
old-location: storage\ioctl_storage_protocol_command.htm
old-project: storage
ms.assetid: 1AA59350-2475-4BF7-B447-42FDDB311882
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_storage_protocol_command, IOCTL_STORAGE_PROTOCOL_COMMAND control code [Storage Devices], IOCTL_STORAGE_PROTOCOL_COMMAND, ntddstor/IOCTL_STORAGE_PROTOCOL_COMMAND
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
-	IOCTL_STORAGE_PROTOCOL_COMMAND
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_ZONE_CONDITION, STORAGE_ZONE_CONDITION"
---

# IOCTL_STORAGE_PROTOCOL_COMMAND IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


A driver can use <b>IOCTL_STORAGE_PROTOCOL_COMMAND</b> to pass vendor-specific commands to a storage device.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the results of the vendor-specific command to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. Cast the structure returned to a <a href="..\ntddstor\ns-ntddstor-_storage_protocol_command.md">STORAGE_PROTOCOL_COMMAND</a> and check its <b>ReturnStatus</b> field to determine the status of the command request.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(<a href="..\ntddstor\ns-ntddstor-_storage_protocol_command.md">STORAGE_PROTOCOL_COMMAND</a>). 


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to <b>STATUS_SUCCESS</b>, or possibly to <b>STATUS_INSUFFICIENT_RESOURCES</b>.


## -see-also

<a href="..\ntddstor\ns-ntddstor-_storage_protocol_command.md">STORAGE_PROTOCOL_COMMAND</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_PROTOCOL_COMMAND control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

