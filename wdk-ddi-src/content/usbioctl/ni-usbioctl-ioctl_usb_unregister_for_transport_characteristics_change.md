---
UID: NI:usbioctl.IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE
title: IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE
author: windows-driver-content
description: This request unregisters the caller from getting notifications about transport characteristics changes.
old-location: buses\ioctl_usb_unregister_for_transport_characteristics_change.htm
tech.root: usbref
ms.assetid: A6D17761-4E5F-42FC-AB40-C2BCE7769243
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE, IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE control, IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE control code [Buses], buses.ioctl_usb_unregister_for_transport_characteristics_change, usbioctl/IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE IOCTL


## -description


This request unregisters the caller from getting notifications about transport characteristics changes.


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://msdn.microsoft.com/22F185EB-103D-4D7D-94B7-D34D48B1C526">USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION</a> structure that contains the registration handle previously received by the <a href="https://msdn.microsoft.com/4192501F-5A30-463C-924D-CD4F2C8C3764">IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE</a> request.


### -input-buffer-length

The size of the <a href="https://msdn.microsoft.com/22F185EB-103D-4D7D-94B7-D34D48B1C526">USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION</a> structure.


### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> indicates the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



After this request completes the registration handle is considered to be stale and requests sent on that handle are failed by the USB driver stack.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/usb-client-drivers-for-ma-usb">USB client drivers for Media-Agnostic (MA-USB)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
 

 

