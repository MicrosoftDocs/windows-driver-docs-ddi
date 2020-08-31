---
UID: NI:ntddcdvd.IOCTL_DVD_READ_STRUCTURE
title: IOCTL_DVD_READ_STRUCTURE (ntddcdvd.h)
description: Returns information about a DVD disc, such as a layer descriptor, copyright information, or manufacturer-specific information.
old-location: storage\ioctl_dvd_read_structure.htm
tech.root: storage
ms.assetid: 64cf4d53-5d03-43bc-b295-37ecf67b4d2a
ms.date: 03/29/2018
keywords: ["IOCTL_DVD_READ_STRUCTURE IOCTL"]
ms.keywords: IOCTL_DVD_READ_STRUCTURE, IOCTL_DVD_READ_STRUCTURE control, IOCTL_DVD_READ_STRUCTURE control code [Storage Devices], k307_eafb209e-3aed-4471-a4e0-a0e52ce4c462.xml, ntddcdvd/IOCTL_DVD_READ_STRUCTURE, storage.ioctl_dvd_read_structure
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
 - IOCTL_DVD_READ_STRUCTURE
 - ntddcdvd/IOCTL_DVD_READ_STRUCTURE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddcdvd.h
api_name:
 - IOCTL_DVD_READ_STRUCTURE
---

# IOCTL_DVD_READ_STRUCTURE IOCTL


## -description

Returns information about a DVD disc, such as a layer descriptor, copyright information, or manufacturer-specific information.

## -ioctlparameters

### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-dvd_read_structure">DVD_READ_STRUCTURE</a> structure that indicates the session ID and type of information to return.

### -input-buffer-length

Length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-dvd_read_structure">DVD_READ_STRUCTURE</a>.

### -output-buffer

The driver returns the disc information in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.

### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the buffer, which must be >= <b>sizeof(</b><i>Descriptor</i><b>)</b> where <i>Descriptor</i> is <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_dvd_layer_descriptor">DVD_LAYER_DESCRIPTOR</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_dvd_copyright_descriptor">DVD_COPYRIGHT_DESCRIPTOR</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_dvd_disk_key_descriptor">DVD_DISK_KEY_DESCRIPTOR</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_dvd_bca_descriptor">DVD_BCA_DESCRIPTOR</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_dvd_manufacturer_descriptor">DVD_MANUFACTURER_DESCRIPTOR</a>.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_dvd_bca_descriptor">DVD_BCA_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_dvd_copyright_descriptor">DVD_COPYRIGHT_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_dvd_disk_key_descriptor">DVD_DISK_KEY_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_dvd_layer_descriptor">DVD_LAYER_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_dvd_manufacturer_descriptor">DVD_MANUFACTURER_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-dvd_read_structure">DVD_READ_STRUCTURE</a>

