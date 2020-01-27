---
UID: NI:hidport.IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST
title: IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST (hidport.h)
description: The IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST control code is the IOCTL of the idle notification request IRP that HIDClass sends to HID mini drivers, such as HIDUSB, to inform the bus driver that the device is now idle.
old-location: hid\ioctl_hid_send_idle_notification_request.htm
tech.root: hid
ms.assetid: AD653C7C-7C43-4258-98F8-3D9EDB51AE44
ms.date: 04/30/2018
ms.keywords: IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST, IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST control, IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST control code [Human Input Devices], hid.ioctl_hid_send_idle_notification_request, hidport/IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST
f1_keywords:
 - "hidport/IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST"
req.header: hidport.h
req.include-header: Hidport.h
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
- Hidport.h
api_name:
- IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST IOCTL


## -description


The <b>IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST</b> 
   control code is the IOCTL of the idle notification request IRP that HIDClass sends to HID mini drivers, such as HIDUSB, to inform the bus driver that the device is now idle.

For general information about HIDClass devices, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code.


### -input-buffer-length

 The size of a status code.


### -output-buffer


       None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The bus or port driver sets Irp->IoStatus.Status to STATUS_SUCCESS or the appropriate error status.

