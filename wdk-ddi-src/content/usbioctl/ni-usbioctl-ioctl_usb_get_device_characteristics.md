---
UID: NI:usbioctl.IOCTL_USB_GET_DEVICE_CHARACTERISTICS
title: IOCTL_USB_GET_DEVICE_CHARACTERISTICS
author: windows-driver-content
description: The client driver sends this request to determine general characteristics about a USB device, such as maximum send and receive delays for any request.
old-location: buses\_ioctl_usb_get_device_characteristics.htm
tech.root: usbref
ms.assetid: FEEF13FE-E7CF-4513-8E16-B1E46283883C
ms.date: 05/07/2018
ms.keywords: IOCTL_USB_GET_DEVICE_CHARACTERISTICS, IOCTL_USB_GET_DEVICE_CHARACTERISTICS control, IOCTL_USB_GET_DEVICE_CHARACTERISTICS control code [Buses], buses._ioctl_usb_get_device_characteristics, usbioctl/ IOCTL_USB_GET_DEVICE_CHARACTERISTICS
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: 
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Usbioctl.h
api_name:
-	IOCTL_USB_GET_DEVICE_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USB_GET_DEVICE_CHARACTERISTICS IOCTL


## -description


The client driver sends this request to determine general characteristics about a USB device, such as maximum send and receive delays for any request.


## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer

The <b>AssociatedIrp.SystemBuffer</b> member is a pointer to a caller-allocated <a href="https://msdn.microsoft.com/D4A8DE43-3E81-4A1C-B1C0-ABE6000D9F11">USB_DEVICE_CHARACTERISTIC</a>S structure.  On input, set <b>Version</b> to USB_DEVICE_CHARACTERISTICS_VERSION_1. On output <b>Version</b> is reset to a version less than or equal to USB_DEVICE_CHARACTERISTICS_VERSION_1;  <b>UsbDeviceCharacteristicsFlags</b> is set to USB_DEVICE_CHARACTERISTICS_MAXIMUM_PATH_DELAYS_AVAILABLE and the remaining members of the structure is filled with delay information.


### -inout-buffer-length

The size of the <a href="https://msdn.microsoft.com/D4A8DE43-3E81-4A1C-B1C0-ABE6000D9F11">USB_DEVICE_CHARACTERISTICS</a> structure.


### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> indicates  the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/usb-client-drivers-for-ma-usb">USB client drivers for Media-Agnostic (MA-USB)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

