---
UID: NF:usbdlib.USBD_CreateConfigurationRequest
title: USBD_CreateConfigurationRequest function
author: windows-driver-content
description: The USBD_CreateConfigurationRequest routine has been deprecated. Use USBD_CreateConfigurationRequestEx instead.
old-location: buses\usbd_createconfigurationrequest.htm
old-project: usbref
ms.assetid: e1f397f6-2f33-4352-9bbc-2b2a49dcd067
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: USBD_CreateConfigurationRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Deprecated. Use USBD_CreateConfigurationRequestEx instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USBD_CreateConfigurationRequest
req.alt-loc: Usbd.lib,Usbd.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Usbd.lib
req.dll: 
req.irql: 
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---

# USBD_CreateConfigurationRequest function



## -description
The  <b>USBD_CreateConfigurationRequest</b> routine has been deprecated. Use <a href="..\usbdlib\nf-usbdlib-usbd_createconfigurationrequestex.md">USBD_CreateConfigurationRequestEx</a> instead.



## -syntax

````
PURB USBD_CreateConfigurationRequest(
  _In_    PUSB_CONFIGURATION_DESCRIPTOR   ConfigurationDescriptor,
  _Inout_ PUSHORT                         Siz
    
);
````


## -parameters

### -param ConfigurationDescriptor [in]

Pointer to a caller-allocated <a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a> structure that contains the configuration descriptor for the configuration to be selected.


### -param Siz
    </i> [in, out]
<dd>
Size of the <a href="..\usb\ns-usb-_urb.md">URB</a> structure.


## -returns
<b>USBD_CreateConfigurationRequest</b> allocates a <a href="..\usb\ns-usb-_urb.md">URB</a> structure, formats it for the URB_FUNCTION_SELECT_CONFIGURATION request (select-configuration request), and returns a pointer to the <b>URB</b>. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\usbdlib\nf-usbdlib-usbd_createconfigurationrequestex.md">USBD_CreateConfigurationRequestEx</a>
</dt>
<dt><a href="usb_reference.htm#client">USB device driver programming reference</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_CreateConfigurationRequest routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

