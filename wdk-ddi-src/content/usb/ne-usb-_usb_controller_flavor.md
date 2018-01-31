---
UID: NE:usb._USB_CONTROLLER_FLAVOR
title: "_USB_CONTROLLER_FLAVOR"
author: windows-driver-content
description: The USB_CONTROLLER_FLAVOR enumeration specifies the type of USB host controller.
old-location: buses\usb_controller_flavor.htm
old-project: usbref
ms.assetid: c732fe90-50fb-4f6e-b42e-cb35c1ed0091
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: usb/OHCI_Generic, EHCI_Generic, usbstrct_a1b79c0b-7ee4-48bd-9793-8f37b9d248f2.xml, usb/OHCI_Hydra, UHCI_Ich4, usb/UHCI_Piix3, usb/UHCI_VIA_x0E_FIFO, usb/EHCI_Generic, UHCI_Ich3m, EHCI_Lucent, usb/EHCI_NEC, usb/UHCI_Ich4, usb/UHCI_Ich2, UHCI_Ich1, usb/USB_CONTROLLER_FLAVOR, UHCI_VIA_x03, usb/EHCI_Intel_Medfield, USB_CONTROLLER_FLAVOR, USB_HcGeneric, EHCI_NVIDIA_Tegra2, usb/UHCI_VIA_x01, _USB_CONTROLLER_FLAVOR, UHCI_VIA_x01, buses.usb_controller_flavor, usb/UHCI_Piix4, EHCI_NVIDIA_Tegra3, usb/UHCI_VIA_x02, usb/UHCI_VIA_x04, usb/UHCI_Generic, EHCI_NEC, UHCI_Piix3, usb/EHCI_NVIDIA_Tegra3, UHCI_VIA_x04, UHCI_VIA_x02, UHCI_VIA_x0E_FIFO, UHCI_Ich5, usb/OHCI_NEC, UHCI_Generic, usb/UHCI_Ich6, usb/UHCI_Intel, UHCI_Intel, usb/UHCI_Ich1, usb/EHCI_Lucent, OHCI_Generic, usb/USB_HcGeneric, UHCI_Ich2, UHCI_VIA, usb/UHCI_VIA_x03, UHCI_Piix4, usb/UHCI_VIA, OHCI_Hydra, usb/UHCI_Ich5, USB_CONTROLLER_FLAVOR enumeration [Buses], usb/EHCI_NVIDIA_Tegra2, OHCI_NEC, usb/UHCI_Ich3m, EHCI_Intel_Medfield, UHCI_Ich6
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
-	USB_CONTROLLER_FLAVOR
product: Windows
targetos: Windows
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




#### - USB_HcGeneric

Indicates a generic host controller.


#### - OHCI_Generic

Indicates a generic OHCI host controller.


#### - OHCI_Hydra

Indicates a Hydra host controller.


#### - OHCI_NEC

Indicates a NEC host controller.


#### - UHCI_Generic

Indicates a generic UHCI host controller.


#### - UHCI_Piix4

Indicates an Intel PIIX4 UHCI host controller.


#### - UHCI_Piix3

Indicates an Intel PIIX3 UHCI host controller.


#### - UHCI_Ich2

Indicates an Intel ICH2 UHCI host controller.


### -field UHCI_Reserved204



#### - UHCI_Ich1

Indicates an Intel 815 ICH1 UHCI host controller.


#### - UHCI_Ich3m

Indicates an Intel ICH3m UHCI host controller.


#### - UHCI_Ich4

Indicates an Intel ICH4m UHCI host controller.


#### - UHCI_Ich5

Indicates an Intel ICH5m UHCI host controller.


#### - UHCI_Ich6

Indicates an Intel ICH6m UHCI host controller.


#### - UHCI_Intel

Indicates a generic Intel UHCI host controller.


#### - UHCI_VIA

Indicates a generic VIA UHCI host controller.


#### - UHCI_VIA_x01

Indicates a Revision 1 VIA UHCI host controller.


#### - UHCI_VIA_x02

Indicates a Revision 2 VIA UHCI host controller.


#### - UHCI_VIA_x03

Indicates a Revision 3 VIA UHCI host controller.


#### - UHCI_VIA_x04

Indicates a Revision 4 VIA UHCI host controller.


#### - UHCI_VIA_x0E_FIFO

Indicates a FIFO Revision VIA UHCI host controller.


#### - EHCI_Generic

Indicates a generic EHCI host controller.


#### - EHCI_NEC

Indicates an NEC EHCI host controller.


#### - EHCI_Lucent

Indicates an EHCI Lucent host controller.


#### - EHCI_NVIDIA_Tegra2

Indicates a Revision 2 NVIDIA Tegra EHCI host controller.


#### - EHCI_NVIDIA_Tegra3

Indicates a Revision 3 NVIDIA Tegra EHCI host controller.


#### - EHCI_Intel_Medfield

Indicates an Intel Medfield host controller.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539256">USB_CONTROLLER_INFO_0</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539322">USB Constants and Enumerations</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_CONTROLLER_FLAVOR enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

