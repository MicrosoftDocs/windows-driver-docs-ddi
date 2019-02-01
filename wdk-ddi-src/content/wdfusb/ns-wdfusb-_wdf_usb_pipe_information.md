---
UID: NS:wdfusb._WDF_USB_PIPE_INFORMATION
title: _WDF_USB_PIPE_INFORMATION (wdfusb.h)
description: The WDF_USB_PIPE_INFORMATION structure contains information about a USB pipe and its endpoint.
old-location: wdf\wdf_usb_pipe_information.htm
tech.root: wdf
ms.assetid: 05cba67b-c9da-4345-bc6f-09de12a617c1
ms.date: 02/26/2018
ms.keywords: "*PWDF_USB_PIPE_INFORMATION, DFUsbRef_80f26f29-adf0-4017-b261-36637da41c0d.xml, PWDF_USB_PIPE_INFORMATION, PWDF_USB_PIPE_INFORMATION structure pointer, WDF_USB_PIPE_INFORMATION, WDF_USB_PIPE_INFORMATION structure, _WDF_USB_PIPE_INFORMATION, kmdf.wdf_usb_pipe_information, wdf.wdf_usb_pipe_information, wdfusb/PWDF_USB_PIPE_INFORMATION, wdfusb/WDF_USB_PIPE_INFORMATION"
ms.topic: struct
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	wdfusb.h
api_name:
-	WDF_USB_PIPE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: WDF_USB_PIPE_INFORMATION, *PWDF_USB_PIPE_INFORMATION
---

# _WDF_USB_PIPE_INFORMATION structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_PIPE_INFORMATION</b> structure contains information about a USB pipe and its endpoint.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field MaximumPacketSize

The maximum packet size, in bytes, that the pipe's endpoint is capable of sending or receiving.

For high-speed isochronous endpoints, the received <b>MaximumPacketSize</b> value includes the number of bytes that can be transferred in additional transactions, if the endpoint supports them.


### -field EndpointAddress

The address of the endpoint on the USB device. For more information about endpoint addresses, see the USB specification.


### -field Interval

The endpoint's polling interval, if the <b>PipeType</b> member is set to <b>WdfUsbPipeTypeInterrupt</b>. For more information about polling intervals, see the USB specification.


### -field SettingIndex

An index value that identifies the alternate setting, within an interface, that the pipe belongs to. For more information about alternate settings, see the USB specification.


### -field PipeType

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff553047">WDF_USB_PIPE_TYPE</a>-typed value that specifies the type of pipe.


### -field MaximumTransferSize

This member is not used.  


## -remarks



The <b>WDF_USB_PIPE_INFORMATION</b> structure is filled in by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551142">WdfUsbTargetPipeGetInformation</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550063">WdfUsbInterfaceGetEndpointInformation</a> methods.

To initialize a <b>WDF_USB_PIPE_INFORMATION</b> structure, your driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff553040">WDF_USB_PIPE_INFORMATION_INIT</a>.

For more information about the <b>MaximumPacketSize</b> member of this structure, see  the Remarks section of <a href="https://msdn.microsoft.com/library/windows/hardware/ff539114">USBD_PIPE_INFORMATION</a>.

For information on how to transfer data to and from supported isochronous endpoints in a USB device, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406225">How to Transfer Data to USB Isochronous Endpoints</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539114">USBD_PIPE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553040">WDF_USB_PIPE_INFORMATION_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553047">WDF_USB_PIPE_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550057">WdfUsbInterfaceGetConfiguredPipe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550063">WdfUsbInterfaceGetEndpointInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551142">WdfUsbTargetPipeGetInformation</a>
 

 

