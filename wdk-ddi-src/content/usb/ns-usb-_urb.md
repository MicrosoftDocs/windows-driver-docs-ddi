---
UID: NS:usb._URB
title: _URB (usb.h)
description: The URB structure is used by USB client drivers to describe USB request blocks (URBs) that send requests to the USB driver stack. The URB structure defines a format for all possible commands that can be sent to a USB device.
old-location: buses\urb.htm
tech.root: usbref
ms.assetid: f28b2c97-61ee-4843-b3c5-b3a55f172c50
ms.date: 05/07/2018
ms.keywords: PURB, PURB structure pointer [Buses], URB, URB structure [Buses], _URB, buses.urb, usb/PURB, usb/URB, usbstrct_20441a98-258d-44d2-b414-67b336a44fac.xml
f1_keywords:
 - "usb/URB"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usb.h
api_name:
- URB
product:
- Windows
targetos: Windows
req.typenames: URB, PURB
---

# _URB structure


## -description


The <b>URB</b> structure is used by USB client drivers to describe USB request blocks (URBs) that send requests to the USB driver stack. The <b>URB</b> structure defines a format for all possible commands that can be sent to a USB device.


## -struct-fields




### -field UrbHeader

Provides basic information about the request being sent to the host controller driver. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_header">_URB_HEADER</a>.


### -field UrbSelectInterface

Defines the format of a select interface command for a USB device. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_select_interface">_URB_SELECT_INTERFACE</a>.


### -field UrbSelectConfiguration

Defines the format of a select configuration command for a USB device. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_select_configuration">_URB_SELECT_CONFIGURATION</a>.


### -field UrbPipeRequest

Defines the format for a command for a  pipe in a USB endpoint. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_pipe_request">_URB_PIPE_REQUEST</a>.


### -field UrbFrameLengthControl

Deprecated in Windows 2000 and later operating systems and is not supported by Microsoft. Do not use. 


### -field UrbGetFrameLength

Deprecated in Windows 2000 and later operating systems and is not supported by Microsoft. Do not use. 


### -field UrbSetFrameLength

Deprecated in Windows 2000 and later operating systems and is not supported by Microsoft. Do not use. 


### -field UrbGetCurrentFrameNumber

Defines the format for a command to get the current frame number on a USB bus. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_get_current_frame_number">_URB_GET_CURRENT_FRAME_NUMBER</a>.


### -field UrbControlTransfer

Defines the format for a command to transmit or receive data on a control pipe. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_control_transfer">_URB_CONTROL_TRANSFER</a>.


### -field UrbControlTransferEx

Defines the format for a command to transmit or receive data on a control pipe. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_control_transfer_ex">_URB_CONTROL_TRANSFER_EX</a>.

Defines the format for a command to transmit or receive data on a control pipe. 


### -field UrbBulkOrInterruptTransfer

Defines the format for a command to transmit or receive data on a bulk pipe, or to receive data from an interrupt pipe. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_bulk_or_interrupt_transfer">_URB_BULK_OR_INTERRUPT_TRANSFER</a>.


### -field UrbIsochronousTransfer

Defines the format of an isochronous transfer to a USB device. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_isoch_transfer">_URB_ISOCH_TRANSFER</a>.


### -field UrbControlDescriptorRequest

Defines the format for a command to retrieve or set descriptor(s) on a USB device. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_control_descriptor_request">_URB_CONTROL_DESCRIPTOR_REQUEST</a>.


### -field UrbControlGetStatusRequest

Defines the format for a command to get status from a device, interface, or endpoint. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_control_get_status_request">_URB_CONTROL_GET_STATUS_REQUEST</a>.


### -field UrbControlFeatureRequest

Defines the format for a command to set or clear USB-defined features on an device, interface, or endpoint. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_control_feature_request">_URB_CONTROL_FEATURE_REQUEST</a>.


### -field UrbControlVendorClassRequest

Defines the format for a command to send or receive a vendor or class-specific request on a device, interface, endpoint, or other device-defined target. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_control_vendor_or_class_request">_URB_CONTROL_VENDOR_OR_CLASS_REQUEST</a>.


### -field UrbControlGetInterfaceRequest

Defines the format for a command to get the current alternate interface setting for a selected interface. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_control_get_interface_request">_URB_CONTROL_GET_INTERFACE_REQUEST</a>.


### -field UrbControlGetConfigurationRequest

Defines the format for a command to get the current configuration for a device. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_control_get_configuration_request">_URB_CONTROL_GET_CONFIGURATION_REQUEST</a>.


### -field UrbOSFeatureDescriptorRequest

Defines the format for a command to request a Microsoft OS Descriptor. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_os_feature_descriptor_request">_URB_OS_FEATURE_DESCRIPTOR_REQUEST</a>.


### -field UrbOpenStaticStreams

Defines the format for a command to open streams in a bulk endpoint of a USB 3.0 device. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_open_static_streams">_URB_OPEN_STATIC_STREAMS</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">How to Open and Close Static Streams in a USB Bulk Endpoint</a>.


### -field UrbGetIsochPipeTransferPathDelays

Defines the format for a command to retrieve delays associated with isochronous transfer programming in the host controller and transfer completion so that the client driver can ensure that the device gets the isochronous packets in time. 
For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_get_isoch_pipe_transfer_path_delays">_URB_GET_ISOCH_PIPE_TRANSFER_PATH_DELAYS</a>.


## -remarks



For information about the function codes to set in each structure, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_header">_URB_HEADER</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_internal_usb_submit_urb">IOCTL_INTERNAL_USB_SUBMIT_URB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">USB Structures</a>
 

 

