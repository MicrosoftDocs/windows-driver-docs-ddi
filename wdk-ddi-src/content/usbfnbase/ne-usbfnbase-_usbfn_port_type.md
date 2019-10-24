---
UID: NE:usbfnbase._USBFN_PORT_TYPE
title: _USBFN_PORT_TYPE (usbfnbase.h)
description: Defines the possible port types that can be returned by the client driver during port detection.
old-location: buses\usbfn_port_type.htm
tech.root: usbref
ms.assetid: D45F8CD0-CB54-4DE4-BD6B-FF6A35FCBFEC
ms.date: 05/07/2018
ms.keywords: "*PUSBFN_PORT_TYPE, USBFN_PORT_TYPE, USBFN_PORT_TYPE enumeration [Buses], UsbfnChargingDownstreamPort, UsbfnDedicatedChargingPort, UsbfnInvalidDedicatedChargingPort, UsbfnPortTypeMaximum, UsbfnProprietaryDedicatedChargingPort, UsbfnStandardDownstreamPort, UsbfnUnknownPort, _USBFN_PORT_TYPE, buses.usbfn_port_type, usbfnbase/USBFN_PORT_TYPE, usbfnbase/UsbfnChargingDownstreamPort, usbfnbase/UsbfnDedicatedChargingPort, usbfnbase/UsbfnInvalidDedicatedChargingPort, usbfnbase/UsbfnPortTypeMaximum, usbfnbase/UsbfnProprietaryDedicatedChargingPort, usbfnbase/UsbfnStandardDownstreamPort, usbfnbase/UsbfnUnknownPort"
ms.topic: enum
f1_keywords:
 - "usbfnbase/USBFN_PORT_TYPE"
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
- USBFN_PORT_TYPE
product:
- Windows
targetos: Windows
req.typenames: USBFN_PORT_TYPE, *PUSBFN_PORT_TYPE
---

# _USBFN_PORT_TYPE enumeration


## -description


Defines the possible port types that can be returned by the client driver during port detection.


## -enum-fields




### -field UsbfnUnknownPort

Port detection was unable to determine the port type.


### -field UsbfnStandardDownstreamPort

The upstream port has been detected as a standard downstream port (SDP) (as defined in the Battery Charging Specification, revision 1.2).


### -field UsbfnChargingDownstreamPort

The upstream port has been detected as a charging downstream port (CDP), as defined in the Battery Charging Specification, revision 1.2.


### -field UsbfnDedicatedChargingPort

The upstream port has been detected as a dedicated charging port (DCP) (as defined in the Battery Charging Specification, revision 1.2).


### -field UsbfnInvalidDedicatedChargingPort

The upstream port has been detected as a dedicated charging port that does not comply with the Battery Charging Specification, revision 1.2.


### -field UsbfnProprietaryDedicatedChargingPort

A proprietary charger was attached.


### -field UsbfnPortTypeMaximum

The maximum value of the enumeration.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnattach/nc-usbfnattach-usbfn_get_attach_action">USBFN_GET_ATTACH_ACTION</a>
 

 

