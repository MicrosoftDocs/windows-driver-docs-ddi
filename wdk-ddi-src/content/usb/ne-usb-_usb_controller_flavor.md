---
UID: NE:usb._USB_CONTROLLER_FLAVOR
title: _USB_CONTROLLER_FLAVOR (usb.h)
description: The USB_CONTROLLER_FLAVOR enumeration specifies the type of USB host controller.
old-location: buses\usb_controller_flavor.htm
tech.root: usbref
ms.assetid: c732fe90-50fb-4f6e-b42e-cb35c1ed0091
ms.date: 05/07/2018
keywords: ["USB_CONTROLLER_FLAVOR enumeration"]
ms.keywords: EHCI_Generic, EHCI_Intel_Medfield, EHCI_Lucent, EHCI_NEC, EHCI_NVIDIA_Tegra2, EHCI_NVIDIA_Tegra3, OHCI_Generic, OHCI_Hydra, OHCI_NEC, UHCI_Generic, UHCI_Ich1, UHCI_Ich2, UHCI_Ich3m, UHCI_Ich4, UHCI_Ich5, UHCI_Ich6, UHCI_Intel, UHCI_Piix3, UHCI_Piix4, UHCI_VIA, UHCI_VIA_x01, UHCI_VIA_x02, UHCI_VIA_x03, UHCI_VIA_x04, UHCI_VIA_x0E_FIFO, USB_CONTROLLER_FLAVOR, USB_CONTROLLER_FLAVOR enumeration [Buses], USB_HcGeneric, _USB_CONTROLLER_FLAVOR, buses.usb_controller_flavor, usb/EHCI_Generic, usb/EHCI_Intel_Medfield, usb/EHCI_Lucent, usb/EHCI_NEC, usb/EHCI_NVIDIA_Tegra2, usb/EHCI_NVIDIA_Tegra3, usb/OHCI_Generic, usb/OHCI_Hydra, usb/OHCI_NEC, usb/UHCI_Generic, usb/UHCI_Ich1, usb/UHCI_Ich2, usb/UHCI_Ich3m, usb/UHCI_Ich4, usb/UHCI_Ich5, usb/UHCI_Ich6, usb/UHCI_Intel, usb/UHCI_Piix3, usb/UHCI_Piix4, usb/UHCI_VIA, usb/UHCI_VIA_x01, usb/UHCI_VIA_x02, usb/UHCI_VIA_x03, usb/UHCI_VIA_x04, usb/UHCI_VIA_x0E_FIFO, usb/USB_CONTROLLER_FLAVOR, usb/USB_HcGeneric, usbstrct_a1b79c0b-7ee4-48bd-9793-8f37b9d248f2.xml
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
targetos: Windows
req.typenames: USB_CONTROLLER_FLAVOR
f1_keywords:
 - _USB_CONTROLLER_FLAVOR
 - usb/_USB_CONTROLLER_FLAVOR
 - USB_CONTROLLER_FLAVOR
 - usb/USB_CONTROLLER_FLAVOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usb.h
api_name:
 - USB_CONTROLLER_FLAVOR
---

# _USB_CONTROLLER_FLAVOR enumeration


## -description

The <b>USB_CONTROLLER_FLAVOR</b> enumeration specifies the type of USB host controller.

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

### -field UHCI_Reserved204

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

## -see-also

<a href="/windows-hardware/drivers/ddi/_usbref/#enumerations">USB Constants and Enumerations</a>



<a href="/windows/win32/api/usbuser/ns-usbuser-usb_controller_info_0">USB_CONTROLLER_INFO_0</a>