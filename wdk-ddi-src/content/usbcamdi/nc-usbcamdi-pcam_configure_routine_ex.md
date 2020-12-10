---
UID: NC:usbcamdi.PCAM_CONFIGURE_ROUTINE_EX
title: PCAM_CONFIGURE_ROUTINE_EX (usbcamdi.h)
description: A camera minidriver's CamConfigureEx callback function configures the isochronous streaming interface.
old-location: stream\camconfigureex.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["PCAM_CONFIGURE_ROUTINE_EX callback function"]
ms.keywords: CamConfigureEx, CamConfigureEx routine [Streaming Media Devices], PCAM_CONFIGURE_ROUTINE_EX, stream.camconfigureex, usbcamdi/CamConfigureEx, usbcmdpr_79d31303-32b2-493e-87b6-d6e1a9ad292d.xml
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
req.target-type: Desktop
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PCAM_CONFIGURE_ROUTINE_EX
 - usbcamdi/PCAM_CONFIGURE_ROUTINE_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbcamdi.h
api_name:
 - CamConfigureEx
---

# PCAM_CONFIGURE_ROUTINE_EX callback function


## -description

A camera minidriver's <b>CamConfigureEx</b> callback function configures the isochronous streaming interface.

## -parameters

### -param BusDeviceObject

Pointer to the camera minidriver's device object created by the USB hub.

### -param DeviceContext

Pointer to the camera minidriver's device context.

### -param Interface

Pointer to the <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_interface_information">USBD_INTERFACE_INFORMATION</a> structure initialized with the proper values for a SELECT_INTERFACE URB request. This interface structure corresponds to a single isochronous interface on the device.

### -param ConfigurationDescriptor

Pointer to the <a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a> for this device.

### -param PipeConfigListSize

Specifies the number of elements in the <i>PipeConfig</i> array.

### -param PipeConfig

Pointer to a <a href="/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-_pipe_config_descriptor">USBCAMD_Pipe_Config_Descriptor</a> array describing the association between pipes and streams.

### -param DeviceDescriptor

Pointer to the <a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a> for this device.

## -returns

<b>CamConfigureEx</b> returns STATUS_SUCCESS or an appropriate error code.

## -remarks

Camera minidrivers use <b>CamConfigureEx</b> to inform USBCAMD about the relationship between discovered pipes and streams.

USBCAMD calls the <b>CamConfigureEx</b> callback function to configure the isochronous streaming interface. After this function returns, USBCAMD can be notified of which interface and which alternate setting within the USB video streaming interface to use for the idle state.

USBCAMD requires that the camera must have a single USB configuration description, and all alternate settings within the USB video streaming interface must have the same number and type of pipes.

The original USBCAMD does not call <b>CamConfigureEx</b>.

This function is required.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-_usbcamd_device_data2">USBCAMD_DEVICE_DATA2</a>



<a href="/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-_pipe_config_descriptor">USBCAMD_Pipe_Config_Descriptor</a>



<a href="/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_interface_information">USBD_INTERFACE_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a>
