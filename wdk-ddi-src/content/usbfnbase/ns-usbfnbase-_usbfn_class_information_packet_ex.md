---
UID: NS:usbfnbase._USBFN_CLASS_INFORMATION_PACKET_EX
title: _USBFN_CLASS_INFORMATION_PACKET_EX (usbfnbase.h)
description: Describes device interface class information associated with a USB interface. This structure can be used to describe single and multi-interface functions.
old-location: buses\usbfn_class_information_packet_ex.htm
tech.root: usbref
ms.date: 02/08/2022
keywords: ["USBFN_CLASS_INFORMATION_PACKET_EX structure"]
ms.keywords: "*PUSBFN_CLASS_INFORMATION_PACKET_EX, PUSBFN_CLASS_INFORMATION_PACKET_EX, PUSBFN_CLASS_INFORMATION_PACKET_EX structure pointer [Buses], USBFN_CLASS_INFORMATION_PACKET_EX, USBFN_CLASS_INFORMATION_PACKET_EX structure [Buses], _USBFN_CLASS_INFORMATION_PACKET_EX, buses.usbfn_class_information_packet_ex, usbfnbase/PUSBFN_CLASS_INFORMATION_PACKET_EX, usbfnbase/USBFN_CLASS_INFORMATION_PACKET_EX"
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
req.typenames: USBFN_CLASS_INFORMATION_PACKET_EX, *PUSBFN_CLASS_INFORMATION_PACKET_EX
f1_keywords:
 - _USBFN_CLASS_INFORMATION_PACKET_EX
 - usbfnbase/_USBFN_CLASS_INFORMATION_PACKET_EX
 - PUSBFN_CLASS_INFORMATION_PACKET_EX
 - usbfnbase/PUSBFN_CLASS_INFORMATION_PACKET_EX
 - USBFN_CLASS_INFORMATION_PACKET_EX
 - usbfnbase/USBFN_CLASS_INFORMATION_PACKET_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbfnbase.h
api_name:
 - _USBFN_CLASS_INFORMATION_PACKET_EX
 - PUSBFN_CLASS_INFORMATION_PACKET_EX
 - USBFN_CLASS_INFORMATION_PACKET_EX
---

# _USBFN_CLASS_INFORMATION_PACKET_EX structure

## -description

Describes device interface class information associated with a USB interface. This structure can be used to describe single and multi-interface functions.

## -struct-fields

### -field FullSpeedClassInterfaceEx

A [USBFN_CLASS_INTERFACE_EX](ns-usbfnbase-_usbfn_class_interface_ex.md) structure that describes an interface for full speed device.

### -field HighSpeedClassInterfaceEx

A  structure that describes an interface for high speed device.

### -field SuperSpeedClassInterfaceEx

A [USBFN_CLASS_INTERFACE_EX](ns-usbfnbase-_usbfn_class_interface_ex.md) structure that describes an interface for SuperSpeed device.

### -field InterfaceName

A string that contains the interface name.

### -field InterfaceGuid

A string from which the driver can derive the device interface GUID.

### -field HasInterfaceGuid

Determines whether the driver has published a device interface is GUID.

## -see-also

- [USBFN_CLASS_INTERFACE_EX](ns-usbfnbase-_usbfn_class_interface_ex.md)
- [WdfDeviceCreateSymbolicLink](../wdfdevice/nf-wdfdevice-wdfdevicecreatesymboliclink.md)
- [WdfDeviceSetDeviceInterfaceStateEx](../wdfdevice/nf-wdfdevice-wdfdevicesetdeviceinterfacestateex.md)
