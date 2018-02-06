---
UID: NC:usbcamdi.PCAM_CONFIGURE_ROUTINE_EX
title: PCAM_CONFIGURE_ROUTINE_EX
author: windows-driver-content
description: A camera minidriver's CamConfigureEx callback function configures the isochronous streaming interface.
old-location: stream\camconfigureex.htm
old-project: stream
ms.assetid: ec9fd207-4ed8-4bc9-b240-b5214e8c7f67
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.camconfigureex, CamConfigureEx, CamConfigureEx routine [Streaming Media Devices], CamConfigureEx, PCAM_CONFIGURE_ROUTINE_EX, PCAM_CONFIGURE_ROUTINE_EX, usbcamdi/CamConfigureEx, usbcmdpr_79d31303-32b2-493e-87b6-d6e1a9ad292d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	usbcamdi.h
apiname:
-	CamConfigureEx
product: Windows
targetos: Windows
req.typenames: "*PUSB_BUS_INTERFACE_USBDI_V3, USB_BUS_INTERFACE_USBDI_V3"
req.product: Windows 10 or later.
---

# PCAM_CONFIGURE_ROUTINE_EX callback


## -description


A camera minidriver's <b>CamConfigureEx</b> callback function configures the isochronous streaming interface.


## -prototype


````
PCAM_CONFIGURE_ROUTINE_EX CamConfigureEx;

NTSTATUS CamConfigureEx(
   PDEVICE_OBJECT                  BusDeviceObject,
   PVOID                           DeviceContext,
   PUSBD_INTERFACE_INFORMATION     Interface,
   PUSB_CONFIGURATION_DESCRIPTOR   ConfigurationDescriptor,
   ULONG                           PipeConfigListSize,
   PUSBCAMD_Pipe_Config_Descriptor PipeConfig,
   PUSB_DEVICE_DESCRIPTOR          DeviceDescriptor
)
{ ... }
````


## -parameters




### -param BusDeviceObject

Pointer to the camera minidriver's device object created by the USB hub.


### -param DeviceContext

Pointer to the camera minidriver's device context.


### -param Interface

Pointer to the <a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a> structure initialized with the proper values for a SELECT_INTERFACE URB request. This interface structure corresponds to a single isochronous interface on the device.


### -param ConfigurationDescriptor

Pointer to the <a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a> for this device.


### -param PipeConfigListSize

Specifies the number of elements in the <i>PipeConfig</i> array.


### -param PipeConfig

Pointer to a <a href="..\usbcamdi\ns-usbcamdi-_pipe_config_descriptor.md">USBCAMD_Pipe_Config_Descriptor</a> array describing the association between pipes and streams.


### -param DeviceDescriptor

Pointer to the <a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a> for this device.


## -returns


<b>CamConfigureEx</b> returns STATUS_SUCCESS or an appropriate error code.



## -remarks


Camera minidrivers use <b>CamConfigureEx</b> to inform USBCAMD about the relationship between discovered pipes and streams.

USBCAMD calls the <b>CamConfigureEx</b> callback function to configure the isochronous streaming interface. After this function returns, USBCAMD can be notified of which interface and which alternate setting within the USB video streaming interface to use for the idle state.

USBCAMD requires that the camera must have a single USB configuration description, and all alternate settings within the USB video streaming interface must have the same number and type of pipes.

The original USBCAMD does not call <b>CamConfigureEx</b>.

This function is required.



## -see-also

<a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a>

<a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a>

<a href="..\usbcamdi\ns-usbcamdi-_pipe_config_descriptor.md">USBCAMD_Pipe_Config_Descriptor</a>

<a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a>

<a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data2.md">USBCAMD_DEVICE_DATA2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PCAM_CONFIGURE_ROUTINE_EX routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

