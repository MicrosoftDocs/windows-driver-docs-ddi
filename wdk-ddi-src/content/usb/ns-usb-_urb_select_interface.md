---
UID: NS:usb._URB_SELECT_INTERFACE
title: "_URB_SELECT_INTERFACE"
author: windows-driver-content
description: The _URB_SELECT_INTERFACE structure is used by USB client drivers to select an alternate setting for an interface or to change the maximum packet size of a pipe in the current configuration on a USB device.
old-location: buses\_urb_select_interface.htm
old-project: usbref
ms.assetid: 48f80c80-49af-4cda-961b-8967e8d4897a
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "_URB_SELECT_INTERFACE, _URB_SELECT_INTERFACE structure [Buses], buses._urb_select_interface, usb/_URB_SELECT_INTERFACE, usbstrct_c23c108d-422b-4dee-a1de-a5e341fc1800.xml"
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
-	_URB_SELECT_INTERFACE
product: Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# _URB_SELECT_INTERFACE structure


## -description


The <b>_URB_SELECT_INTERFACE</b> structure is used by USB client drivers to select an alternate setting for an interface or to change the maximum packet size of a pipe in the current configuration on a USB device.


## -struct-fields




### -field Hdr

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540409">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be URB_FUNCTION_SELECT_INTERFACE, and <b>Hdr.Length</b> must be the size of the entire URB.


### -field ConfigurationHandle

Specifies the handle to the configuration that this interface belongs to. The host controller driver returns this handle when the client selects the configuration with an URB_FUNCTION_SELECT_CONFIGURATION request.


### -field Interface

A variable-length <a href="https://msdn.microsoft.com/library/windows/hardware/ff539068">USBD_INTERFACE_INFORMATION</a> structure that specifies the interface and the new alternate setting for that interface, and if required, the new maximum packet sizes for the corresponding pipes. For more information, see Remarks.


## -remarks



You can use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537164">GET_SELECT_INTERFACE_REQUEST_SIZE</a> macro to determine the size of the URB_FUNCTION_SELECT_INTERFACE URB, and the <b>UsbBuildSelectInterfaceRequest</b> routine to format the URB.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff539068">USBD_INTERFACE_INFORMATION</a> structure contains information about the interface and its alternate setting.  The <b>Pipes</b> member of <b>USBD_INTERFACE_INFORMATION</b> points to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff539114">USBD_PIPE_INFORMATION</a> structures. The array stores information about the  pipes associated with the endpoints of the interface. You can override certain default settings for a pipe, such as its maximum packet size. To alter the maximum packet size, set the USBD_PF_CHANGE_MAX_PACKET flag in <code>Pipes[i].PipeFlags</code>, and then specify the new value in <code>Pipes[i].MaximumPacketSize</code>. 

 After the bus driver successfully completes processing the URB_FUNCTION_SELECT_INTERFACE URB, it returns an array of handles for each pipe in the  <code>Pipes[i].PipeHandle</code>  member. The client driver can store pipe handles to send I/O requests to specific pipes.




## -see-also




<a href="https://msdn.microsoft.com/710b4f96-eeee-4313-b068-b2f2e718f8d2">Configuring USB Devices</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539068">USBD_INTERFACE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540409">_URB_HEADER</a>
 

 

