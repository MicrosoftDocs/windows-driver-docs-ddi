---
UID: NS:usbspec._USB_CONFIGURATION_DESCRIPTOR
title: "_USB_CONFIGURATION_DESCRIPTOR"
author: windows-driver-content
description: The USB_CONFIGURATION_DESCRIPTOR structure is used by USB client drivers to hold a USB-defined configuration descriptor.
old-location: buses\usb_configuration_descriptor.htm
old-project: usbref
ms.assetid: 2a9398f7-4d01-42a6-9ac2-ca105db76bb8
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: usbstrct_f057519c-8b38-479c-9065-16c2106550aa.xml, USB_CONFIGURATION_DESCRIPTOR, buses.usb_configuration_descriptor, PUSB_CONFIGURATION_DESCRIPTOR structure pointer [Buses], PUSB_CONFIGURATION_DESCRIPTOR, _USB_CONFIGURATION_DESCRIPTOR, USB_CONFIGURATION_DESCRIPTOR structure [Buses], usbspec/PUSB_CONFIGURATION_DESCRIPTOR, usbspec/USB_CONFIGURATION_DESCRIPTOR, *PUSB_CONFIGURATION_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbspec.h
req.include-header: Usb100.h
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
-	usbspec.h
apiname:
-	USB_CONFIGURATION_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: USB_CONFIGURATION_DESCRIPTOR, *PUSB_CONFIGURATION_DESCRIPTOR
req.product: Windows 10 or later.
---

# _USB_CONFIGURATION_DESCRIPTOR structure


## -description


The  <b>USB_CONFIGURATION_DESCRIPTOR</b> structure is used by USB client drivers to hold a USB-defined configuration descriptor.


## -syntax


````
typedef struct _USB_CONFIGURATION_DESCRIPTOR {
  UCHAR  bLength;
  UCHAR  bDescriptorType;
  USHORT wTotalLength;
  UCHAR  bNumInterfaces;
  UCHAR  bConfigurationValue;
  UCHAR  iConfiguration;
  UCHAR  bmAttributes;
  UCHAR  MaxPower;
} USB_CONFIGURATION_DESCRIPTOR, *PUSB_CONFIGURATION_DESCRIPTOR;
````


## -struct-fields




### -field bLength

Specifies the length, in bytes, of this structure.


### -field bDescriptorType

Specifies the descriptor type. Must be set to USB_CONFIGURATION_DESCRIPTOR_TYPE.


### -field wTotalLength

Specifies the total length, in bytes, of all data for the configuration. The length includes all interface, endpoint, class, or vendor-specific descriptors that are returned with the configuration descriptor.


### -field bNumInterfaces

Specifies the total number of interfaces supported by this configuration.


### -field bConfigurationValue

Contains the value that is used to select a configuration. This value is passed to the USB SetConfiguration request , as described in version 1.1 of the Universal Serial Bus Specification. The port driver does not currently expose a service that allows higher-level drivers to set the configuration. 


### -field iConfiguration

Specifies the device-defined index of the string descriptor for this configuration.


### -field bmAttributes

Specifies a bitmap to describe behavior of this configuration. The bits are described and set in little-endian order.

<table>
<tr>
<th>Bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0 - 4

</td>
<td>
Reserved.

</td>
</tr>
<tr>
<td>
5

</td>
<td>
The configuration supports remote wakeup.

</td>
</tr>
<tr>
<td>
6

</td>
<td>
The configuration is self-powered and does not use power from the bus.

</td>
</tr>
<tr>
<td>
7

</td>
<td>
The configuration is powered by the bus.

</td>
</tr>
</table>
 


### -field MaxPower

Specifies the power requirements of this device in two-milliampere units. This member is valid only if bit seven is set in <b>bmAttributes</b>.


## -remarks



If <b>wTotalLength</b> is greater than the buffer size provided in the URB to hold all descriptors retrieved (interface, endpoint, class, and vendor-defined), incomplete data will be returned. In order to retrieve complete descriptors, the request will need to be re-sent with a larger buffer.

If <b>bmAttributes</b> bits six and seven are both set, then the device is powered both by the bus and by a source external to the bus.

Other members that are part of this structure but not described here should be treated as opaque and considered to be reserved for system use.




## -see-also

<a href="..\usbdlib\nf-usbdlib-usbd_createconfigurationrequest.md">USBD_CreateConfigurationRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538943">UsbBuildGetDescriptorRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_CONFIGURATION_DESCRIPTOR structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

