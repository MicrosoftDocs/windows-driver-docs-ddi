---
UID: NI:ntddchgr.IOCTL_CHANGER_MOVE_MEDIUM
title: IOCTL_CHANGER_MOVE_MEDIUM
author: windows-driver-content
description: Moves a piece of media from a source element to a destination.
old-location: storage\ioctl_changer_move_medium.htm
old-project: storage
ms.assetid: 4a410f56-cdc1-4cb0-801c-62402caec4ee
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_CHANGER_MOVE_MEDIUM, IOCTL_CHANGER_MOVE_MEDIUM control, IOCTL_CHANGER_MOVE_MEDIUM control code [Storage Devices], k307_4d55c834-2f72-433b-8e75-015908324d87.xml, ntddchgr/IOCTL_CHANGER_MOVE_MEDIUM, storage.ioctl_changer_move_medium
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddchgr.h
req.include-header: Ntddchgr.h
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
-	Ntddchgr.h
api_name:
-	IOCTL_CHANGER_MOVE_MEDIUM
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CHANGER_MOVE_MEDIUM IOCTL


## -description



Moves a piece of media from a source element to a destination.




## -ioctlparameters




### -input-buffer


       The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551474">CHANGER_MOVE_MEDIUM</a> data, which indicates the transport to use for the operation, the source, the destination, and whether the medium should be flipped, assuming the device supports two-sided media. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(CHANGER_MOVE_MEDIUM). 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to <b>sizeof</b>(CHANGER_MOVE_MEDIUM). The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_DESTINATION_ELEMENT_FULL, STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, STATUS_INVALID_DEVICE_REQUEST, STATUS_INVALID_ELEMENT_ADDRESS, STATUS_INVALID_PARAMETER, or STATUS_SOURCE_ELEMENT_EMPTY. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551474">CHANGER_MOVE_MEDIUM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551436">ChangerMoveMedium</a>
 

 

