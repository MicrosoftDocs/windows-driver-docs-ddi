---
UID: NS:usbfnbase._USBFN_CLASS_INFORMATION_PACKET
title: _USBFN_CLASS_INFORMATION_PACKET (usbfnbase.h)
description: Describes device interface class information associated with a USB interface. This structure can only hold information about a single function interface.
old-location: buses\usbfn_class_information_packet.htm
tech.root: usbref
ms.date: 02/08/2022
keywords: ["USBFN_CLASS_INFORMATION_PACKET structure"]
ms.keywords: "*PUSBFN_CLASS_INFORMATION_PACKET, PUSBFN_CLASS_INFORMATION_PACKET, PUSBFN_CLASS_INFORMATION_PACKET structure pointer [Buses], USBFN_CLASS_INFORMATION_PACKET, USBFN_CLASS_INFORMATION_PACKET structure [Buses], _USBFN_CLASS_INFORMATION_PACKET, buses.usbfn_class_information_packet, usbfnbase/PUSBFN_CLASS_INFORMATION_PACKET, usbfnbase/USBFN_CLASS_INFORMATION_PACKET"
req.header: usbfnbase.h
req.include-header: 
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
req.typenames: USBFN_CLASS_INFORMATION_PACKET, *PUSBFN_CLASS_INFORMATION_PACKET
f1_keywords:
 - _USBFN_CLASS_INFORMATION_PACKET
 - usbfnbase/_USBFN_CLASS_INFORMATION_PACKET
 - PUSBFN_CLASS_INFORMATION_PACKET
 - usbfnbase/PUSBFN_CLASS_INFORMATION_PACKET
 - USBFN_CLASS_INFORMATION_PACKET
 - usbfnbase/USBFN_CLASS_INFORMATION_PACKET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbfnbase.h
api_name:
 - _USBFN_CLASS_INFORMATION_PACKET
 - PUSBFN_CLASS_INFORMATION_PACKET
 - USBFN_CLASS_INFORMATION_PACKET
---

# _USBFN_CLASS_INFORMATION_PACKET structure

## -description

Describes device interface class information associated with a USB interface. This structure can only hold information about a single function interface.

## -struct-fields

### -field FullSpeedClassInterface

A [USBFN_CLASS_INTERFACE](ns-usbfnbase-_usbfn_class_interface.md) structure that describes an interface for full speed device.

### -field HighSpeedClassInterface

A [USBFN_CLASS_INTERFACE](ns-usbfnbase-_usbfn_class_interface.md) structure that describes an interface for high speed device.

### -field InterfaceName

A string that contains the interface name.

### -field InterfaceGuid

A string from which the driver can derive the device interface GUID.

### -field HasInterfaceGuid

Determines whether the driver has published a device interface is GUID.

### -field SuperSpeedClassInterface

A [USBFN_CLASS_INTERFACE](ns-usbfnbase-_usbfn_class_interface.md) structure that describes an interface for SuperSpeed device.

## -see-also

- [USBFN_CLASS_INTERFACE](ns-usbfnbase-_usbfn_class_interface.md)
- [WdfDeviceCreateSymbolicLink](../wdfdevice/nf-wdfdevice-wdfdevicecreatesymboliclink.md)
- [WdfDeviceSetDeviceInterfaceState](../wdfdevice/nf-wdfdevice-wdfdevicesetdeviceinterfacestate.md)
