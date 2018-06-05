---
UID: NI:ntddcdvd.IOCTL_DVD_READ_STRUCTURE
title: IOCTL_DVD_READ_STRUCTURE
author: windows-driver-content
description: Returns information about a DVD disc, such as a layer descriptor, copyright information, or manufacturer-specific information.
old-location: storage\ioctl_dvd_read_structure.htm
old-project: storage
ms.assetid: 64cf4d53-5d03-43bc-b295-37ecf67b4d2a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_DVD_READ_STRUCTURE, IOCTL_DVD_READ_STRUCTURE control, IOCTL_DVD_READ_STRUCTURE control code [Storage Devices], k307_eafb209e-3aed-4471-a4e0-a0e52ce4c462.xml, ntddcdvd/IOCTL_DVD_READ_STRUCTURE, storage.ioctl_dvd_read_structure
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddcdvd.h
api_name:
-	IOCTL_DVD_READ_STRUCTURE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DVD_READ_STRUCTURE IOCTL


## -description



Returns information about a DVD disc, such as a layer descriptor, copyright information, or manufacturer-specific information.




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553738">DVD_READ_STRUCTURE</a> structure that indicates the session ID and type of information to return. 


### -input-buffer-length

Length of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553738">DVD_READ_STRUCTURE</a>.


### -output-buffer

The driver returns the disc information in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof(</b><i>Descriptor</i><b>)</b> where <i>Descriptor</i> is <a href="https://msdn.microsoft.com/library/windows/hardware/ff553733">DVD_LAYER_DESCRIPTOR</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff553715">DVD_COPYRIGHT_DESCRIPTOR</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff553724">DVD_DISK_KEY_DESCRIPTOR</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff553713">DVD_BCA_DESCRIPTOR</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff553736">DVD_MANUFACTURER_DESCRIPTOR</a>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553713">DVD_BCA_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553715">DVD_COPYRIGHT_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553724">DVD_DISK_KEY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553733">DVD_LAYER_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553736">DVD_MANUFACTURER_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553738">DVD_READ_STRUCTURE</a>
 

 

