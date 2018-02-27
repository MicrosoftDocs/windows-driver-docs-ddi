---
UID: NI:usbprint.IOCTL_USBPRINT_GET_LPT_STATUS
title: IOCTL_USBPRINT_GET_LPT_STATUS
author: windows-driver-content
description: The IOCTL_USBPRINT_GET_LPT_STATUS request allows upper-layer software (such as a language monitor), to request and obtain the printer status byte from a USB printer.
old-location: print\ioctl_usbprint_get_lpt_status.htm
old-project: print
ms.assetid: 706e62f9-1be6-43bd-812a-dbb459877909
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IOCTL_USBPRINT_GET_LPT_STATUS, IOCTL_USBPRINT_GET_LPT_STATUS control code [Print Devices], print.ioctl_usbprint_get_lpt_status, usbioctl_1729d0c7-8762-426e-bdb8-aa0bf38f71ee.xml, usbprint/IOCTL_USBPRINT_GET_LPT_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbprint.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbprint.h
apiname:
-	IOCTL_USBPRINT_GET_LPT_STATUS
product: Windows
targetos: Windows
req.typenames: USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION, *PUSB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION
req.product: Windows 10 or later.
---

# IOCTL_USBPRINT_GET_LPT_STATUS IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_USBPRINT_GET_LPT_STATUS</b> request allows upper-layer software (such as a language monitor), to request and obtain the printer status byte from a USB printer.


## -ioctlparameters




### -input-buffer

Not used in this operation; set this parameter to <b>NULL</b>. A pointer to a UCHAR input buffer.


### -input-buffer-length

Not used in this operation; set this parameter to 0. The size of the input buffer, in bytes.


### -output-buffer

A pointer to the output buffer, which consists of UCHAR data. On success this buffer holds the following: a two-byte prefix that specifies the size, in bytes, of the device's IEEE 1284 device ID; the device ID; and a null terminator. An IEEE 1284 device ID can be up to 64 KB in size. On failure, if <b>GetLastError</b> returns the error code <b>ERROR_FILE_NOT_FOUND</b>, this buffer contains the value <b>BATTERY_TAG_INVALID</b>.


### -output-buffer-length

The size of the output buffer, in bytes.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



To retrieve a handle to the device, you must call the <b>CreateFile</b> function with either the name of a device or the name of the driver associated with a device. To specify a device name, use the following format:

\\.\DeviceName

<b>DeviceIoControl</b> can accept a handle to a specific device. For example, to open a handle to the logical drive A: with <b>CreateFile</b>, specify \\.\a:. Alternatively, you can use the names \\.\PhysicalDrive0, \\.\PhysicalDrive1, and so on, to open handles to the physical drives on a system.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IOCTL_USBPRINT_GET_LPT_STATUS control code%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

