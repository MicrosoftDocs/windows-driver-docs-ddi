---
UID: NI:ntddstor.IOCTL_STORAGE_GET_MEDIA_SERIAL_NUMBER
title: IOCTL_STORAGE_GET_MEDIA_SERIAL_NUMBER
author: windows-driver-content
description: Queries the USB generic parent driver for the serial number of a USB device.
old-location: storage\ioctl_storage_get_media_serial_number.htm
old-project: storage
ms.assetid: aa903b7e-e844-466e-85b1-33fe6ba40689
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _STORAGE_ZONE_CONDITION, STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_STORAGE_GET_MEDIA_SERIAL_NUMBER
req.alt-loc: Ntddstor.h
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
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_GET_MEDIA_SERIAL_NUMBER IOCTL



## -description

Queries the USB generic parent driver for the serial number of a USB device. If a USB device has a CSM-1 content security interface, a USB client driver can query for its serial number using this request. USB client drivers that help implement a digital rights management (DRM) system can use this information to ensure that only legitimate customers have access to digitized intellectual property. 



Queries the USB generic parent driver for the serial number of a USB device. If a USB device has a CSM-1 content security interface, a USB client driver can query for its serial number using this request. USB client drivers that help implement a digital rights management (DRM) system can use this information to ensure that only legitimate customers have access to digitized intellectual property. 



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The driver returns the serial number of the indicated device in a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff562213">MEDIA_SERIAL_NUMBER_DATA</a> in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b>(MEDIA_SERIAL_NUMBER_DATA).


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to the size, in bytes, of the returned data. The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INVALID_BUFFER_SIZE or STATUS_INSUFFICIENT_RESOURCES.


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562213">MEDIA_SERIAL_NUMBER_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_GET_MEDIA_SERIAL_NUMBER control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

