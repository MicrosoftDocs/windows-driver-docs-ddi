---
UID: NI:ntddcdvd.IOCTL_DVD_READ_STRUCTURE
title: IOCTL_DVD_READ_STRUCTURE
author: windows-driver-content
description: Returns information about a DVD disc, such as a layer descriptor, copyright information, or manufacturer-specific information.
old-location: storage\ioctl_dvd_read_structure.htm
old-project: storage
ms.assetid: 64cf4d53-5d03-43bc-b295-37ecf67b4d2a
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_DVD_READ_STRUCTURE, IOCTL_DVD_READ_STRUCTURE control code [Storage Devices], k307_eafb209e-3aed-4471-a4e0-a0e52ce4c462.xml, ntddcdvd/IOCTL_DVD_READ_STRUCTURE, storage.ioctl_dvd_read_structure
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddcdvd.h
apiname:
-	IOCTL_DVD_READ_STRUCTURE
product: Windows
targetos: Windows
req.typenames: DVD_STRUCTURE_FORMAT, *PDVD_STRUCTURE_FORMAT
---

# IOCTL_DVD_READ_STRUCTURE IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Returns information about a DVD disc, such as a layer descriptor, copyright information, or manufacturer-specific information.




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="..\ntddcdvd\ns-ntddcdvd-dvd_read_structure.md">DVD_READ_STRUCTURE</a> structure that indicates the session ID and type of information to return. 


### -input-buffer-length

Length of a <a href="..\ntddcdvd\ns-ntddcdvd-dvd_read_structure.md">DVD_READ_STRUCTURE</a>.


### -output-buffer

The driver returns the disc information in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof(</b><i>Descriptor</i><b>)</b> where <i>Descriptor</i> is <a href="..\ntddcdvd\ns-ntddcdvd-_dvd_layer_descriptor.md">DVD_LAYER_DESCRIPTOR</a>, <a href="..\ntddcdvd\ns-ntddcdvd-_dvd_copyright_descriptor.md">DVD_COPYRIGHT_DESCRIPTOR</a>, <a href="..\ntddcdvd\ns-ntddcdvd-_dvd_disk_key_descriptor.md">DVD_DISK_KEY_DESCRIPTOR</a>, <a href="..\ntddcdvd\ns-ntddcdvd-_dvd_bca_descriptor.md">DVD_BCA_DESCRIPTOR</a>, or <a href="..\ntddcdvd\ns-ntddcdvd-_dvd_manufacturer_descriptor.md">DVD_MANUFACTURER_DESCRIPTOR</a>.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.


## -see-also

<a href="..\ntddcdvd\ns-ntddcdvd-dvd_read_structure.md">DVD_READ_STRUCTURE</a>



<a href="..\ntddcdvd\ns-ntddcdvd-_dvd_disk_key_descriptor.md">DVD_DISK_KEY_DESCRIPTOR</a>



<a href="..\ntddcdvd\ns-ntddcdvd-_dvd_manufacturer_descriptor.md">DVD_MANUFACTURER_DESCRIPTOR</a>



<a href="..\ntddcdvd\ns-ntddcdvd-_dvd_layer_descriptor.md">DVD_LAYER_DESCRIPTOR</a>



<a href="..\ntddcdvd\ns-ntddcdvd-_dvd_copyright_descriptor.md">DVD_COPYRIGHT_DESCRIPTOR</a>



<a href="..\ntddcdvd\ns-ntddcdvd-_dvd_bca_descriptor.md">DVD_BCA_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DVD_READ_STRUCTURE control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

