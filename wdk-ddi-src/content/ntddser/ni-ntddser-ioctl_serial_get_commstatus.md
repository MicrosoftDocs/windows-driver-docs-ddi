---
UID: NI:ntddser.IOCTL_SERIAL_GET_COMMSTATUS
title: IOCTL_SERIAL_GET_COMMSTATUS
author: windows-driver-content
description: The IOCTL_SERIAL_GET_COMMSTATUS request returns information about the communication status of a serial device. For more information about the status information that is retrieved by this request, see SERIAL_STATUS.
old-location: serports\ioctl_serial_get_commstatus.htm
old-project: serports
ms.assetid: 70d0efe3-5ba1-4552-8c58-83c3f14e2264
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SERIAL_GET_COMMSTATUS, IOCTL_SERIAL_GET_COMMSTATUS control code [Serial Ports], ntddser/IOCTL_SERIAL_GET_COMMSTATUS, serports.ioctl_serial_get_commstatus, serref_4c26c2fc-2285-4b46-8791-0fb613e1c05a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddser.h
req.include-header: Ntddser.h
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
-	Ntddser.h
api_name:
-	IOCTL_SERIAL_GET_COMMSTATUS
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_GET_COMMSTATUS IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_SERIAL_GET_COMMSTATUS</b> request returns information about the communication status of a serial device. For more information about the status information that is retrieved by this request, see <a href="..\ntddser\ns-ntddser-_serial_status.md">SERIAL_STATUS</a>.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated <b>SERIAL_STATUS</b> structure that the serial controller driver uses to output communication status information.


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size in bytes of a <b>SERIAL_STATUS</b> structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the request is successful, the <b>Information</b> member is set to the size in bytes of a <b>SERIAL_STATUS</b> structure. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -see-also

<a href="..\ntddser\ns-ntddser-_serial_status.md">SERIAL_STATUS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_GET_COMMSTATUS control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

