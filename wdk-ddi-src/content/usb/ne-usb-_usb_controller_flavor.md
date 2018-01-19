---
UID: NE:usb._USB_CONTROLLER_FLAVOR
title: _USB_CONTROLLER_FLAVOR
author: windows-driver-content
description: The USB_CONTROLLER_FLAVOR enumeration specifies the type of USB host controller.
old-location: buses\usb_controller_flavor.htm
old-project: usbref
ms.assetid: c732fe90-50fb-4f6e-b42e-cb35c1ed0091
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _USB_CONTROLLER_FLAVOR, USB_CONTROLLER_FLAVOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: usb.h
req.include-header: Usb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USB_CONTROLLER_FLAVOR
req.alt-loc: usb.h
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
req.typenames: USB_CONTROLLER_FLAVOR
req.product: Windows 10 or later.
---

# _USB_CONTROLLER_FLAVOR enumeration



## -description
The <b>USB_CONTROLLER_FLAVOR</b> enumeration specifies the type of USB host controller.



## -syntax

````
typedef enum _USB_CONTROLLER_FLAVOR { 
  USB_HcGeneric        = 0,
  OHCI_Generic         = 100,
  OHCI_Hydra           = 101,
  OHCI_NEC             = 102,
  UHCI_Generic         = 200,
  UHCI_Piix4           = 201,
  UHCI_Piix3           = 202,
  UHCI_Ich2            = 203,
  UHCI_Ich1            = 205,
  UHCI_Ich3m           = 206,
  UHCI_Ich4            = 207,
  UHCI_Ich5            = 208,
  UHCI_Ich6            = 209,
  UHCI_Intel           = 249,
  UHCI_VIA             = 250,
  UHCI_VIA_x01         = 251,
  UHCI_VIA_x02         = 252,
  UHCI_VIA_x03         = 253,
  UHCI_VIA_x04         = 254,
  UHCI_VIA_x0E_FIFO    = 264,
  EHCI_Generic         = 1000,
  EHCI_NEC             = 2000,
  EHCI_Lucent          = 3000,
  EHCI_NVIDIA_Tegra2   = 4000,
  EHCI_NVIDIA_Tegra3   = 4001,
  EHCI_Intel_Medfield  = 5001
} USB_CONTROLLER_FLAVOR;
````


## -enum-fields

### -field USB_HcGeneric

Indicates a generic host controller.


### -field OHCI_Generic

Indicates a generic OHCI host controller.


### -field OHCI_Hydra

Indicates a Hydra host controller.


### -field OHCI_NEC

Indicates a NEC host controller.


### -field UHCI_Generic

Indicates a generic UHCI host controller.


### -field UHCI_Piix4

Indicates an Intel PIIX4 UHCI host controller.


### -field UHCI_Piix3

Indicates an Intel PIIX3 UHCI host controller.


### -field UHCI_Ich2

Indicates an Intel ICH2 UHCI host controller.


### -field UHCI_Ich1

Indicates an Intel 815 ICH1 UHCI host controller.


### -field UHCI_Ich3m

Indicates an Intel ICH3m UHCI host controller.


### -field UHCI_Ich4

Indicates an Intel ICH4m UHCI host controller.


### -field UHCI_Ich5

Indicates an Intel ICH5m UHCI host controller.


### -field UHCI_Ich6

Indicates an Intel ICH6m UHCI host controller.


### -field UHCI_Intel

Indicates a generic Intel UHCI host controller.


### -field UHCI_VIA

Indicates a generic VIA UHCI host controller.


### -field UHCI_VIA_x01

Indicates a Revision 1 VIA UHCI host controller.


### -field UHCI_VIA_x02

Indicates a Revision 2 VIA UHCI host controller.


### -field UHCI_VIA_x03

Indicates a Revision 3 VIA UHCI host controller.


### -field UHCI_VIA_x04

Indicates a Revision 4 VIA UHCI host controller.


### -field UHCI_VIA_x0E_FIFO

Indicates a FIFO Revision VIA UHCI host controller.


### -field EHCI_Generic

Indicates a generic EHCI host controller.


### -field EHCI_NEC

Indicates an NEC EHCI host controller.


### -field EHCI_Lucent

Indicates an EHCI Lucent host controller.


### -field EHCI_NVIDIA_Tegra2

Indicates a Revision 2 NVIDIA Tegra EHCI host controller.


### -field EHCI_NVIDIA_Tegra3

Indicates a Revision 3 NVIDIA Tegra EHCI host controller.


### -field EHCI_Intel_Medfield

Indicates an Intel Medfield host controller.


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539256">USB_CONTROLLER_INFO_0</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539322">USB Constants and Enumerations</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_CONTROLLER_FLAVOR enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

