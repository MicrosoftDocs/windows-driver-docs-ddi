---
UID: NI:ntddcdvd.IOCTL_DVD_GET_REGION
title: IOCTL_DVD_GET_REGION (ntddcdvd.h)
description: Returns Region Playback Control (RPC) information for a DVD device, such as whether the player supports the RPC2 standard, the current region code of the player, and the remaining number of times the player's region code can be changed by the user.
old-location: storage\ioctl_dvd_get_region.htm
tech.root: storage
ms.assetid: 2c3d6962-1d72-47e7-aa7c-226e5a3aa3d4
ms.date: 03/29/2018
keywords: ["IOCTL_DVD_GET_REGION IOCTL"]
ms.keywords: IOCTL_DVD_GET_REGION, IOCTL_DVD_GET_REGION control, IOCTL_DVD_GET_REGION control code [Storage Devices], k307_74494f73-c80e-4ca6-adec-03d4ca6d335e.xml, ntddcdvd/IOCTL_DVD_GET_REGION, storage.ioctl_dvd_get_region
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_DVD_GET_REGION
 - ntddcdvd/IOCTL_DVD_GET_REGION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddcdvd.h
api_name:
 - IOCTL_DVD_GET_REGION
---

# IOCTL_DVD_GET_REGION IOCTL


## -description

Returns Region Playback Control (RPC) information for a DVD device, such as whether the player supports the RPC2 standard, the current region code of the player, and the remaining number of times the player's region code can be changed by the user. This IOCTL also indicates the region code of the currently mounted disc. This only works if a DVD is in the drive. The <a href="/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_dvd_read_key">IOCTL_DVD_READ_KEY</a> operation should be used to obtain only the device region code. If the drive region has not been set previously (if it is still at factory default) and if the inserted media has a region, the device region will be set to the current media region.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The driver returns the <a href="/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_dvd_region">DVD_REGION</a> data in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.

### -output-buffer-length

None. <b>Parameters.DeviceIoControl.OutputBufferLength</b> indicates the size, in bytes, of the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>, which must be >= <b>sizeof(</b>DVD_REGION<b>)</b>.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_dvd_region">DVD_REGION</a>