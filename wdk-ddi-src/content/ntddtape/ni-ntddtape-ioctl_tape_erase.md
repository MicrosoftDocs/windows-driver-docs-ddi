---
UID: NI:ntddtape.IOCTL_TAPE_ERASE
title: IOCTL_TAPE_ERASE
author: windows-driver-content
description: Erases the current tape partition, either as a TAPE_ERASE_LONG (in other words, a &#0034;secure&#0034;) operation that overwrites data with a pattern or as a TAPE_ERASE_SHORT (in other words, a &#0034;quick&#0034;) operation that writes an end-of-recorded-data mark at the current position.
old-location: storage\ioctl_tape_erase.htm
old-project: storage
ms.assetid: 75ec5c40-1ac2-472a-9923-26018eb6267c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_TAPE_ERASE, IOCTL_TAPE_ERASE control code [Storage Devices], k307_cdbe0ea5-0d23-4ab0-9d37-2832d2367b81.xml, ntddtape/IOCTL_TAPE_ERASE, storage.ioctl_tape_erase
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
-	IOCTL_TAPE_ERASE
product: Windows
targetos: Windows
req.typenames: TAPE_DRIVE_PROBLEM_TYPE
---

# IOCTL_TAPE_ERASE IOCTL


## -description



Erases the current tape partition, either as a TAPE_ERASE_LONG (in other words, a "secure") operation that overwrites data with a pattern or as a TAPE_ERASE_SHORT (in other words, a "quick") operation that writes an end-of-recorded-data mark at the current position.




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a structure of type <a href="..\ntddtape\ns-ntddtape-_tape_erase.md">TAPE_ERASE</a>. 

If the <b>Immediate</b> member is <b>TRUE</b>, the operation should be asynchronous. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(TAPE_ERASE). 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_DEVICE_DATA_ERROR, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_IO_DEVICE_ERROR, STATUS_MEDIA_WRITE_PROTECTED, STATUS_INSUFFICIENT_RESOURCES, STATUS_NOT_IMPLEMENTED, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_VERIFY_REQUIRED.


## -see-also

<a href="..\ntddtape\ns-ntddtape-_tape_erase.md">TAPE_ERASE</a>



<a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567933">TapeMiniErase</a>



 

 


