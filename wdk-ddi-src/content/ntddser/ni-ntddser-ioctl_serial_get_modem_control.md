---
UID: NI:ntddser.IOCTL_SERIAL_GET_MODEM_CONTROL
title: IOCTL_SERIAL_GET_MODEM_CONTROL
author: windows-driver-content
description: The IOCTL_SERIAL_GET_MODEM_CONTROL request returns the value of the modem control register in the serial controller.
old-location: serports\ioctl_serial_get_modem_control.htm
old-project: serports
ms.assetid: 4b3f52ee-8028-4cba-a8c7-4ba73b1fcab0
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SERIAL_GET_MODEM_CONTROL, IOCTL_SERIAL_GET_MODEM_CONTROL control code [Serial Ports], ntddser/IOCTL_SERIAL_GET_MODEM_CONTROL, serports.ioctl_serial_get_modem_control, serref_063be160-c01f-40c9-aff9-2de802c70bda.xml
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
-	IOCTL_SERIAL_GET_MODEM_CONTROL
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_GET_MODEM_CONTROL IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_SERIAL_GET_MODEM_CONTROL</b> request returns the value of the modem control register in the serial controller.

To set the modem control register, a client can use an <a href="..\ntddser\ni-ntddser-ioctl_serial_set_modem_control.md">IOCTL_SERIAL_SET_MODEM_CONTROL</a> request.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated ULONG buffer that the serial controller driver uses to output the value of the modem control register.


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a ULONG.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a ULONG. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.


## -remarks



The <b>IOCTL_SERIAL_GET_MODEM_CONTROL</b> and <b>IOCTL_SERIAL_SET_MODEM_CONTROL</b> requests are used primarily for hardware testing. No standard register layout is defined for the modem control operations. Peripheral drivers that use these IOCTLs risk making themselves dependent on the hardware features of a particular serial controller.

For an example layout of a modem control register, see the definition of the MCR bits (SERIAL_MCR_DTR through SERIAL_MCR_LOOP) in the Serial.h header file in the <a href="http://go.microsoft.com/fwlink/p/?LinkId=617962">Serial driver sample</a> on GitHub.




## -see-also

<a href="..\ntddser\ni-ntddser-ioctl_serial_set_modem_control.md">IOCTL_SERIAL_SET_MODEM_CONTROL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_GET_MODEM_CONTROL control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

