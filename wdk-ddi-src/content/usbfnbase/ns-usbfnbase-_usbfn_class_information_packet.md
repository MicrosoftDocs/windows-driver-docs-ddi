---
UID: NS:usbfnbase._USBFN_CLASS_INFORMATION_PACKET
title: _USBFN_CLASS_INFORMATION_PACKET (usbfnbase.h)
description: Describes device interface class information associated with a USB interface. This structure can only hold information about a single function interface.
old-location: buses\usbfn_class_information_packet.htm
tech.root: usbref
ms.assetid: 18A07670-B610-4D09-8BF0-3C55E781A68B
ms.date: 05/07/2018
keywords: ["_USBFN_CLASS_INFORMATION_PACKET structure"]
ms.keywords: "*PUSBFN_CLASS_INFORMATION_PACKET, PUSBFN_CLASS_INFORMATION_PACKET, PUSBFN_CLASS_INFORMATION_PACKET structure pointer [Buses], USBFN_CLASS_INFORMATION_PACKET, USBFN_CLASS_INFORMATION_PACKET structure [Buses], _USBFN_CLASS_INFORMATION_PACKET, buses.usbfn_class_information_packet, usbfnbase/PUSBFN_CLASS_INFORMATION_PACKET, usbfnbase/USBFN_CLASS_INFORMATION_PACKET"
f1_keywords:
 - "usbfnbase/USBFN_CLASS_INFORMATION_PACKET"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usbfnbase.h
api_name:
- USBFN_CLASS_INFORMATION_PACKET
product:
- Windows
targetos: Windows
req.typenames: USBFN_CLASS_INFORMATION_PACKET, *PUSBFN_CLASS_INFORMATION_PACKET
---

# _USBFN_CLASS_INFORMATION_PACKET structure


## -description


Describes device interface class information associated with a USB interface. This structure can only hold information about a single function interface.


## -struct-fields




### -field FullSpeedClassInterface

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_class_interface">USBFN_CLASS_INTERFACE</a> structure that describes an interface for full speed device.


### -field HighSpeedClassInterface

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_class_interface">USBFN_CLASS_INTERFACE</a> structure that describes an interface for high speed device.


### -field InterfaceName

 


### -field InterfaceGuid

 


### -field HasInterfaceGuid

Determines whether the driver has published a device interface is GUID. 


### -field SuperSpeedClassInterface

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_class_interface">USBFN_CLASS_INTERFACE</a> structure that describes an interface for SuperSpeed device.


#### - InterfaceGuid[MAX_INTERFACE_GUID_LENGTH]

A string from which the driver can derive the device interface GUID.


#### - InterfaceName[MAX_INTERFACE_NAME_LENGTH]

A string that contains the interface name.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnbase/ns-usbfnbase-_usbfn_class_interface">USBFN_CLASS_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreatesymboliclink">WdfDeviceCreateSymbolicLink</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicesetdeviceinterfacestate">WdfDeviceSetDeviceInterfaceState</a>
 

 

