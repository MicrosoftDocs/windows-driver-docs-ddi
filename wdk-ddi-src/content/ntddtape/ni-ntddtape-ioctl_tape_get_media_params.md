---
UID: NI:ntddtape.IOCTL_TAPE_GET_MEDIA_PARAMS
title: IOCTL_TAPE_GET_MEDIA_PARAMS
author: windows-driver-content
description: Returns information about the media's total and remaining capacity, its block size, the number of partitions, and whether it is write-protected.
old-location: storage\ioctl_tape_get_media_params.htm
tech.root: storage
ms.assetid: 4fd09b30-d63b-4b7f-9f6c-ef028e5e549f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_TAPE_GET_MEDIA_PARAMS, IOCTL_TAPE_GET_MEDIA_PARAMS control, IOCTL_TAPE_GET_MEDIA_PARAMS control code [Storage Devices], k307_c8991fab-1c8d-4792-9ecc-6bb7e4643e68.xml, ntddtape/IOCTL_TAPE_GET_MEDIA_PARAMS, storage.ioctl_tape_get_media_params
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
-	IOCTL_TAPE_GET_MEDIA_PARAMS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_TAPE_GET_MEDIA_PARAMS IOCTL


## -description



Returns information about the media's total and remaining capacity, its block size, the number of partitions, and whether it is write-protected.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567965">TAPE_GET_MEDIA_PARAMETERS</a> data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. For a description of the TAPE_GET_MEDIA_PARAMETERS structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567937">TapeMiniGetMediaParameters</a>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(TAPE_GET_MEDIA_PARAMETERS).


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_IO_DEVICE_ERROR, STATUS_DEVICE_DATA_ERROR, STATUS_DATA_OVERRUN, STATUS_NO_SUCH_DEVICE, STATUS_IO_TIMEOUT, STATUS_DEVICE_NOT_READY, STATUS_INFO_LENGTH_MISMATCH, STATUS_NO_MEDIA_IN_DEVICE, or STATUS_VERIFY_REQUIRED.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567965">TAPE_GET_MEDIA_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567975">TAPE_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567937">TapeMiniGetMediaParameters</a>
 

 

