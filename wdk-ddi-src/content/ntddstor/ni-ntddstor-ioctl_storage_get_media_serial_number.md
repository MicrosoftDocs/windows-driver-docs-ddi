---
UID: NI:ntddstor.IOCTL_STORAGE_GET_MEDIA_SERIAL_NUMBER
title: IOCTL_STORAGE_GET_MEDIA_SERIAL_NUMBER (ntddstor.h)
description: Queries the USB generic parent driver for the serial number of a USB device.
old-location: storage\ioctl_storage_get_media_serial_number.htm
tech.root: storage
ms.assetid: aa903b7e-e844-466e-85b1-33fe6ba40689
ms.date: 03/29/2018
keywords: ["IOCTL_STORAGE_GET_MEDIA_SERIAL_NUMBER IOCTL"]
ms.keywords: IOCTL_STORAGE_GET_MEDIA_SERIAL_NUMBER, IOCTL_STORAGE_GET_MEDIA_SERIAL_NUMBER control, IOCTL_STORAGE_GET_MEDIA_SERIAL_NUMBER control code [Storage Devices], k307_dd8dcdec-9756-435c-abbb-14dd1a64ee11.xml, ntddstor/IOCTL_STORAGE_GET_MEDIA_SERIAL_NUMBER, storage.ioctl_storage_get_media_serial_number
f1_keywords:
 - "ntddstor/IOCTL_STORAGE_GET_MEDIA_SERIAL_NUMBER"
 - "IOCTL_STORAGE_GET_MEDIA_SERIAL_NUMBER"
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddstor.h
api_name:
- IOCTL_STORAGE_GET_MEDIA_SERIAL_NUMBER
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_GET_MEDIA_SERIAL_NUMBER IOCTL


## -description



Queries the USB generic parent driver for the serial number of a USB device. If a USB device has a CSM-1 content security interface, a USB client driver can query for its serial number using this request. USB client drivers that help implement a digital rights management (DRM) system can use this information to ensure that only legitimate customers have access to digitized intellectual property. 




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the serial number of the indicated device in a structure of type <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff562213(v=vs.85)">MEDIA_SERIAL_NUMBER_DATA</a> in the buffer at <b>Irp->AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b>(MEDIA_SERIAL_NUMBER_DATA).


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the size, in bytes, of the returned data. The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INVALID_BUFFER_SIZE or STATUS_INSUFFICIENT_RESOURCES.


## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff562213(v=vs.85)">MEDIA_SERIAL_NUMBER_DATA</a>
 

 

