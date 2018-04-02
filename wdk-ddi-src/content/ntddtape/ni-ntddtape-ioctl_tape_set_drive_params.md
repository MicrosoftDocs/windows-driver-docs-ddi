---
UID: NI:ntddtape.IOCTL_TAPE_SET_DRIVE_PARAMS
title: IOCTL_TAPE_SET_DRIVE_PARAMS
author: windows-driver-content
description: Adjusts a tape drive's configurable parameters.
old-location: storage\ioctl_tape_set_drive_params.htm
old-project: storage
ms.assetid: aa625cbf-fa0f-420a-b8ec-2babf4c4ec17
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_TAPE_SET_DRIVE_PARAMS, IOCTL_TAPE_SET_DRIVE_PARAMS control code [Storage Devices], k307_8467b086-c211-4e26-ac65-2d12ea1c4c73.xml, ntddtape/IOCTL_TAPE_SET_DRIVE_PARAMS, storage.ioctl_tape_set_drive_params
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
-	IOCTL_TAPE_SET_DRIVE_PARAMS
product: Windows
targetos: Windows
req.typenames: TAPE_DRIVE_PROBLEM_TYPE
---

# IOCTL_TAPE_SET_DRIVE_PARAMS IOCTL


## -description



Adjusts a tape drive's configurable parameters. The miniclass driver can ignore parameters that its device does not support. The calling application is responsible for determining whether a device supports a particular feature before attempting to set it.




## -ioctlparameters




### -input-buffer


       The <a href="https://msdn.microsoft.com/library/windows/hardware/ff567972">TAPE_SET_DRIVE_PARAMETERS</a> structure in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the values to be set. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(TAPE_SET_DRIVE_PARAMETERS). 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_IO_DEVICE_ERROR, STATUS_INVALID_DEVICE_REQUEST, STATUS_DEVICE_DATA_ERROR, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_INFO_LENGTH_MISMATCH, or STATUS_DEVICE_NOT_READY.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567972">TAPE_SET_DRIVE_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567975">TAPE_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567952">TapeMiniSetDriveParameters</a>
 

 

