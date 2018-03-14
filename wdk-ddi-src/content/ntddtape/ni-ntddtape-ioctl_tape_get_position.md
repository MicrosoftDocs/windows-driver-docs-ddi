---
UID: NI:ntddtape.IOCTL_TAPE_GET_POSITION
title: IOCTL_TAPE_GET_POSITION
author: windows-driver-content
description: Returns the current absolute, logical, or pseudological partition and offset position on the tape.
old-location: storage\ioctl_tape_get_position.htm
old-project: storage
ms.assetid: 358c3089-7238-4604-add8-575b611b3bc9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_TAPE_GET_POSITION, IOCTL_TAPE_GET_POSITION control code [Storage Devices], k307_88069692-1167-4a21-914b-505e1100f6dc.xml, ntddtape/IOCTL_TAPE_GET_POSITION, storage.ioctl_tape_get_position
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddtape.h
req.include-header: Ntddtape.h
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
-	Ntddtape.h
api_name:
-	IOCTL_TAPE_GET_POSITION
product: Windows
targetos: Windows
req.typenames: TAPE_DRIVE_PROBLEM_TYPE
---

# IOCTL_TAPE_GET_POSITION IOCTL


## -description



Returns the current absolute, logical, or pseudological partition and offset position on the tape.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the <a href="..\ntddtape\ns-ntddtape-_tape_get_position.md">TAPE_GET_POSITION</a> data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(TAPE_GET_POSITION).


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_IO_DEVICE_ERROR, STATUS_DEVICE_DATA_ERROR, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_DEVICE_NOT_READY, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_VERIFY_REQUIRED.


## -see-also

<a href="..\ntddtape\ns-ntddtape-_tape_get_position.md">TAPE_GET_POSITION</a>



<a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567946">TapeMiniGetPosition</a>



 

 


