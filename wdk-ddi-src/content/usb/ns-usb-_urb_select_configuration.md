---
UID: NS:usb._URB_SELECT_CONFIGURATION
title: "_URB_SELECT_CONFIGURATION"
author: windows-driver-content
description: The _URB_SELECT_CONFIGURATION structure is used by client drivers to select a configuration for a USB device.
old-location: buses\_urb_select_configuration.htm
old-project: usbref
ms.assetid: a6a4963b-64d7-4f46-bc19-16925929e7c7
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: "_URB_SELECT_CONFIGURATION, usb/_URB_SELECT_CONFIGURATION, usbstrct_cfe530e7-f16f-4d45-96e9-e1603bde77b9.xml, _URB_SELECT_CONFIGURATION structure [Buses], buses._urb_select_configuration"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usb.h
apiname:
-	_URB_SELECT_CONFIGURATION
product: Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# _URB_SELECT_CONFIGURATION structure


## -description


The <b>_URB_SELECT_CONFIGURATION</b> structure is used by client drivers to select a configuration for a USB device.


## -syntax


````
struct _URB_SELECT_CONFIGURATION {
  struct URB_HEADER  Hdr;
  PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor;
  USBD_CONFIGURATION_HANDLE     ConfigurationHandle;
  USBD_INTERFACE_INFORMATION    Interface;
};
````


## -struct-fields




### -field Hdr

Pointer to a <a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be URB_FUNCTION_SELECT_CONFIGURATION, and <b>Hdr.Length</b> must be the size of the entire URB. Drivers may use the GET_SELECT_CONFIGURATION_REQUEST_SIZE macro defined in usbdlib.h to obtain the size of the URB. 


### -field _URB_HEADER

 


### -field ConfigurationDescriptor

Pointer to an initialized USB configuration descriptor that identifies the configuration to be used on the device. If this member is <b>NULL</b>, the device will be set to an unconfigured state.


### -field ConfigurationHandle

Contains a handle that is used to access this configuration on return from the host controller driver. USB client drivers must treat this member as opaque.


### -field Interface

Specifies a variable length array of <a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a> structures, each describing an interface supported by the configuration being selected.

Before the request is sent to the host controller driver, the driver may select an alternate setting for one or more of the interfaces contained in this array by setting members of the <a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a> structure for that interface. 

On return from the host controller driver, this member contains a <a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a> structure with data describing the capabilities and format of the endpoints within that interface.


## -remarks



An URB_FUNCTION_SELECT_CONFIGURATION URB consists of a <b>_URB_SELECT_CONFIGURATION</b> structure followed by a sequence of variable-length array of <a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a> structures, each element in the array for each unique interface number in the configuration. Client drivers must allocate enough memory to contain one <a href="..\usb\ns-usb-_usbd_pipe_information.md">USBD_PIPE_INFORMATION</a> structure for each endpoint in the selected interfaces. 

Drivers can use the <a href="..\usbdlib\nf-usbdlib-usbd_createconfigurationrequestex.md">USBD_CreateConfigurationRequestEx</a> service routine to allocate the URB.

Other members that are part of this structure but not described here should be treated as opaque and considered to be reserved for system use.
   




## -see-also

<a href="..\usb\ns-usb-_urb.md">URB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="..\usbdlib\nf-usbdlib-usbd_createconfigurationrequestex.md">USBD_CreateConfigurationRequestEx</a>



<a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a>



<a href="..\usb\ns-usb-_usbd_pipe_information.md">USBD_PIPE_INFORMATION</a>



<a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20_URB_SELECT_CONFIGURATION structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

