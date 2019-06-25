---
UID: NI:hidclass.IOCTL_HID_DEVICERESET_NOTIFICATION
title: IOCTL_HID_DEVICERESET_NOTIFICATION (hidclass.h)
description: The IOCTL_HID_DEVICERESET_NOTIFICATION request is sent by the HID client driver to HID class driver to wait for a device-initiated reset event.
old-location: hid\ioctl_hid_devicereset_notification.htm
tech.root: hid
ms.assetid: 3A9047BE-C974-45E1-89C7-BF0A5F58DD8B
ms.date: 04/30/2018
ms.keywords: IOCTL_HID_DEVICERESET_NOTIFICATION, IOCTL_HID_DEVICERESET_NOTIFICATION control, IOCTL_HID_DEVICERESET_NOTIFICATION control code [Human Input Devices], hid.ioctl_hid_devicereset_notification, hidclass/IOCTL_HID_DEVICERESET_NOTIFICATION
ms.topic: ioctl
req.header: hidclass.h
req.include-header: Hidclass.h
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
- hidclass.h
api_name:
- IOCTL_HID_DEVICERESET_NOTIFICATION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_DEVICERESET_NOTIFICATION IOCTL


## -description


The <b>IOCTL_HID_DEVICERESET_NOTIFICATION</b> 
   request is sent by the HID client driver to HID class driver to wait for a device-initiated reset event. This request can also be sent by the HID Class driver to the HID Minidriver to wait for a device-initiated reset event.

Only one device reset notification request is allowed at any one  time.

A HID minidriver can enable this feature by adding a registry value in the INF file. The <b>DeviceResetNotificationEnabled</b> under the device's hardware key must be set to 1 to enable the feature. Here is an example:

<code>[hidi2c_Device.NT.HW]
AddReg = hidi2c_Device.Filter.AddReg, hidi2c_Device.Configuration.AddReg
</code>

...






<code>[hidi2c_Device.Configuration.AddReg]</code>

...


<code>HKR,,"DeviceResetNotificationEnabled",0x00010001,1
</code>




## -ioctlparameters




### -input-buffer


       None.


### -input-buffer-length

None.


### -output-buffer


       None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

I<b>rp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 

