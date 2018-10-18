---
UID: NI:ntddcdrm.IOCTL_CDROM_SET_SPEED
title: IOCTL_CDROM_SET_SPEED
author: windows-driver-content
description: Sets the spindle speed of the CD-ROM drive.
old-location: storage\ioctl_cdrom_set_speed.htm
tech.root: storage
ms.assetid: 14acc5f4-1346-4da4-b692-01396cff776e
ms.date: 3/29/2018
ms.keywords: IOCTL_CDROM_SET_SPEED, IOCTL_CDROM_SET_SPEED control, IOCTL_CDROM_SET_SPEED control code [Storage Devices], k307_df26ae09-2af1-4290-812a-b0f279112d97.xml, ntddcdrm/IOCTL_CDROM_SET_SPEED, storage.ioctl_cdrom_set_speed
ms.topic: ioctl
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
-	Ntddcdrm.h
api_name:
-	IOCTL_CDROM_SET_SPEED
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CDROM_SET_SPEED IOCTL


## -description


Sets the spindle speed of the CD-ROM drive.


## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains either a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551368">CDROM_SET_SPEED</a> structure or a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551369">CDROM_SET_STREAMING</a> structure. These two structures have the same first member: an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551370">CDROM_SPEED_REQUEST</a> enumeration value. Caller uses this enumeration value to specify which of these two structures is in the input buffer.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the buffer.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, if the operation succeeds, to STATUS_INFO_LENGTH_MISMATCH (ERROR_BAD_LENGTH) if the input buffer was too small, to STATUS_INVALID_DEVICE_REQUEST (ERROR_INVALID_FUNCTION), if the device does not support the request, or the device is not a Mount Ranier reWriteable (MRW)-compliant device, and to STATUS_INVALID_PARAMETER (ERROR_INVALID_PARAMETER, if the indicated request type is invalid.


## -remarks



For an explanation of function and purpose of this request, see <a href="https://msdn.microsoft.com/25a46b23-f823-4fc7-a370-cab1c9418a94">CD-ROM Set Speed</a>.



