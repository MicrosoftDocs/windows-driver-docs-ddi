---
UID: NC:usbcamdi.PCAM_CONFIGURE_ROUTINE
title: PCAM_CONFIGURE_ROUTINE
author: windows-driver-content
description: A camera minidriver's CamConfigure callback function configures the isochronous streaming interface.
old-location: stream\camconfigure.htm
old-project: stream
ms.assetid: b17fa32e-0a58-4be4-a096-e486471c1cdd
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: stream.camconfigure, CamConfigure, CamConfigure callback function [Streaming Media Devices], CamConfigure, PCAM_CONFIGURE_ROUTINE, PCAM_CONFIGURE_ROUTINE, usbcamdi/CamConfigure, usbcmdpr_4953051b-2fb0-4dd4-ac52-67da188ce7e1.xml
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
-	CamConfigure
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---

# PCAM_CONFIGURE_ROUTINE callback


## -description


<p class="CCE_Message">[CamConfigure is not supported and may be altered or unavailable in the future. Instead, use <a href="..\usbcamdi\nc-usbcamdi-pcam_configure_routine_ex.md">CamConfigureEx</a>.
]

A camera minidriver's <b>CamConfigure</b> callback function configures the isochronous streaming interface.


## -prototype


````
NTSTATUS CamConfigure(
   PDEVICE_OBJECT                BusDeviceObject,
   PVOID                         DeviceContext,
   PUSBD_INTERFACE_INFORMATION   Interface,
   PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor,
   PLONG                         DataPipeIndex,
   PLONG                         SyncPipeIndex
);
````


## -parameters




### -param BusDeviceObject

Pointer to the camera minidriver's device object created by the USB hub.


### -param DeviceContext

Pointer to the camera minidriver's device context.


### -param Interface

Pointer to a <a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a> structure initialized with the proper values for a SELECT_INTERFACE URB request. This interface structure corresponds to a single isochronous interface on the device.


### -param ConfigurationDescriptor

Pointer to an initialized <a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a> for this device.


### -param DataPipeIndex

Pointer to a value that indicates the index of the data pipe. The camera minidriver should fill in this value before returning.


### -param SyncPipeIndex

Pointer to a value that indicates the index of the sync pipe, if one is needed. The camera minidriver should fill in this value before returning.


## -returns



<b>CamConfigure</b> returns STATUS_SUCCESS or an appropriate error code.




## -remarks



Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data.md">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the camera minidriver's <b>CamConfigure</b> callback function to configure the isochronous streaming interface. After this function returns, USBCAMD can be notified of which interface and which alternate setting within the USB video streaming interface to use for the idle state.

This function is required.




## -see-also

<a href="..\usbcamdi\nc-usbcamdi-pcam_configure_routine_ex.md">CamConfigureEx</a>



<a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a>



<a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PCAM_CONFIGURE_ROUTINE callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

