---
UID: NC:usbcamdi.PCAM_CONFIGURE_ROUTINE
title: PCAM_CONFIGURE_ROUTINE (usbcamdi.h)
description: A camera minidriver's CamConfigure callback function configures the isochronous streaming interface.
old-location: stream\camconfigure.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["PCAM_CONFIGURE_ROUTINE callback function"]
ms.keywords: CamConfigure, CamConfigure callback function [Streaming Media Devices], PCAM_CONFIGURE_ROUTINE, PCAM_CONFIGURE_ROUTINE callback, stream.camconfigure, usbcamdi/CamConfigure, usbcmdpr_4953051b-2fb0-4dd4-ac52-67da188ce7e1.xml
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
 - PCAM_CONFIGURE_ROUTINE
 - usbcamdi/PCAM_CONFIGURE_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - usbcamdi.h
api_name:
 - PCAM_CONFIGURE_ROUTINE
---

# PCAM_CONFIGURE_ROUTINE callback function


## -description

<p class="CCE_Message">[CamConfigure is not supported and may be altered or unavailable in the future. Instead, use <a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_configure_routine_ex">CamConfigureEx</a>.
]

A camera minidriver's <b>CamConfigure</b> callback function configures the isochronous streaming interface.

## -parameters

### -param BusDeviceObject

Pointer to the camera minidriver's device object created by the USB hub.

### -param DeviceContext

Pointer to the camera minidriver's device context.

### -param Interface

Pointer to a <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_interface_information">USBD_INTERFACE_INFORMATION</a> structure initialized with the proper values for a SELECT_INTERFACE URB request. This interface structure corresponds to a single isochronous interface on the device.

### -param ConfigurationDescriptor

Pointer to an initialized <a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a> for this device.

### -param DataPipeIndex

Pointer to a value that indicates the index of the data pipe. The camera minidriver should fill in this value before returning.

### -param SyncPipeIndex

Pointer to a value that indicates the index of the sync pipe, if one is needed. The camera minidriver should fill in this value before returning.

## -returns

<b>CamConfigure</b> returns STATUS_SUCCESS or an appropriate error code.

## -remarks

Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="/windows-hardware/drivers/ddi/usbcamdi/ns-usbcamdi-_usbcamd_device_data">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the camera minidriver's <b>CamConfigure</b> callback function to configure the isochronous streaming interface. After this function returns, USBCAMD can be notified of which interface and which alternate setting within the USB video streaming interface to use for the idle state.

This function is required.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_configure_routine_ex">CamConfigureEx</a>



<a href="/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_interface_information">USBD_INTERFACE_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a>

