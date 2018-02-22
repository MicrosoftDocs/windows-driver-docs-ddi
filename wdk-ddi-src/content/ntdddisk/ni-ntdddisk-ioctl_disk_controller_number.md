---
UID: NI:ntdddisk.IOCTL_DISK_CONTROLLER_NUMBER
title: IOCTL_DISK_CONTROLLER_NUMBER
author: windows-driver-content
description: Retrieves the controller number and disk number for an IDE disk.
old-location: storage\ioctl_disk_controller_number.htm
old-project: storage
ms.assetid: dbf7829b-c5b9-4428-a296-34199a726ec5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.ioctl_disk_controller_number, IOCTL_DISK_CONTROLLER_NUMBER control code [Storage Devices], IOCTL_DISK_CONTROLLER_NUMBER, ntdddisk/IOCTL_DISK_CONTROLLER_NUMBER, k307_227ab511-78ff-4aba-be29-3429329d05e5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntdddisk.h
apiname:
-	IOCTL_DISK_CONTROLLER_NUMBER
product: Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_CONTROLLER_NUMBER IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Retrieves the controller number and disk number for an IDE disk.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the <a href="..\ntdddisk\ns-ntdddisk-_disk_controller_number.md">DISK_CONTROLLER_NUMBER</a> data.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the IO_STACK_LOCATION structure of the IRP indicates the size, in bytes, of the output buffer, which must be &gt;= <b>sizeof</b>(DISK_CONTROLLER_NUMBER).


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to <b>sizeof</b>(DISK_CONTROLLER_NUMBER).

The <b>Status</b> field is set to STATUS_SUCCESS if the operation is successful. One possible status value is STATUS_BUFFER_TOO_SMALL if the output buffer provided by the caller is too small. 


## -see-also

<a href="..\ntdddisk\ns-ntdddisk-_disk_controller_number.md">DISK_CONTROLLER_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DISK_CONTROLLER_NUMBER control code%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

