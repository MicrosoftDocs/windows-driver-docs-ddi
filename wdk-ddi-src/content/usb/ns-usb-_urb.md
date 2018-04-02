---
UID: NS:usb._URB
title: "_URB"
author: windows-driver-content
description: The URB structure is used by USB client drivers to describe USB request blocks (URBs) that send requests to the USB driver stack. The URB structure defines a format for all possible commands that can be sent to a USB device.
old-location: buses\urb.htm
old-project: usbref
ms.assetid: f28b2c97-61ee-4843-b3c5-b3a55f172c50
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PURB, PURB structure pointer [Buses], URB, URB structure [Buses], _URB, buses.urb, usb/PURB, usb/URB, usbstrct_20441a98-258d-44d2-b414-67b336a44fac.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usb.h
req.include-header: Usb.h
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
-	usb.h
api_name:
-	URB
product: Windows
targetos: Windows
req.typenames: URB, PURB
req.product: Windows 10 or later.
---

# _URB structure


## -description


The <b>URB</b> structure is used by USB client drivers to describe USB request blocks (URBs) that send requests to the USB driver stack. The <b>URB</b> structure defines a format for all possible commands that can be sent to a USB device.


## -struct-fields






#### - UrbBulkOrInterruptTransfer

Defines the format for a command to transmit or receive data on a bulk pipe, or to receive data from an interrupt pipe. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540352">_URB_BULK_OR_INTERRUPT_TRANSFER</a>.


#### - UrbControlDescriptorRequest

Defines the format for a command to retrieve or set descriptor(s) on a USB device. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540357">_URB_CONTROL_DESCRIPTOR_REQUEST</a>.


#### - UrbControlFeatureRequest

Defines the format for a command to set or clear USB-defined features on an device, interface, or endpoint. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540361">_URB_CONTROL_FEATURE_REQUEST</a>.


#### - UrbControlGetConfigurationRequest

Defines the format for a command to get the current configuration for a device. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540365">_URB_CONTROL_GET_CONFIGURATION_REQUEST</a>.


#### - UrbControlGetInterfaceRequest

Defines the format for a command to get the current alternate interface setting for a selected interface. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540373">_URB_CONTROL_GET_INTERFACE_REQUEST</a>.


#### - UrbControlGetStatusRequest

Defines the format for a command to get status from a device, interface, or endpoint. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540378">_URB_CONTROL_GET_STATUS_REQUEST</a>.


#### - UrbControlTransfer

Defines the format for a command to transmit or receive data on a control pipe. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540384">_URB_CONTROL_TRANSFER</a>.


#### - UrbControlTransferEx

Defines the format for a command to transmit or receive data on a control pipe. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540387">_URB_CONTROL_TRANSFER_EX</a>.

Defines the format for a command to transmit or receive data on a control pipe. 


#### - UrbControlVendorClassRequest

Defines the format for a command to send or receive a vendor or class-specific request on a device, interface, endpoint, or other device-defined target. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540393">_URB_CONTROL_VENDOR_OR_CLASS_REQUEST</a>.


#### - UrbFrameLengthControl

Deprecated in Windows 2000 and later operating systems and is not supported by Microsoft. Do not use. 


#### - UrbGetCurrentFrameNumber

Defines the format for a command to get the current frame number on a USB bus. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540401">_URB_GET_CURRENT_FRAME_NUMBER</a>.


#### - UrbGetFrameLength

Deprecated in Windows 2000 and later operating systems and is not supported by Microsoft. Do not use. 


#### - UrbGetIsochPipeTransferPathDelays

Defines the format for a command to retrieve delays associated with isochronous transfer programming in the host controller and transfer completion so that the client driver can ensure that the device gets the isochronous packets in time. 
For more information, see <a href="https://msdn.microsoft.com/70B74088-C537-4104-A535-F41A24BB72A5">_URB_GET_ISOCH_PIPE_TRANSFER_PATH_DELAYS</a>.


#### - UrbHeader

Provides basic information about the request being sent to the host controller driver. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540409">_URB_HEADER</a>.


#### - UrbIsochronousTransfer

Defines the format of an isochronous transfer to a USB device. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540414">_URB_ISOCH_TRANSFER</a>.


#### - UrbOSFeatureDescriptorRequest

Defines the format for a command to request a Microsoft OS Descriptor. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540417">_URB_OS_FEATURE_DESCRIPTOR_REQUEST</a>.


#### - UrbOpenStaticStreams

Defines the format for a command to open streams in a bulk endpoint of a USB 3.0 device. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406294">_URB_OPEN_STATIC_STREAMS</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh450846">How to Open and Close Static Streams in a USB Bulk Endpoint</a>.


#### - UrbPipeRequest

Defines the format for a command for a  pipe in a USB endpoint. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540419">_URB_PIPE_REQUEST</a>.


#### - UrbSelectConfiguration

Defines the format of a select configuration command for a USB device. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540422">_URB_SELECT_CONFIGURATION</a>.


#### - UrbSelectInterface

Defines the format of a select interface command for a USB device. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540425">_URB_SELECT_INTERFACE</a>.


#### - UrbSetFrameLength

Deprecated in Windows 2000 and later operating systems and is not supported by Microsoft. Do not use. 


## -remarks



For information about the function codes to set in each structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540409">_URB_HEADER</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537271">IOCTL_INTERNAL_USB_SUBMIT_URB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>
 

 

