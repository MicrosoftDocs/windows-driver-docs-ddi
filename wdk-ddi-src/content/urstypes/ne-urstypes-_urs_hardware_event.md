---
UID: NE:urstypes._URS_HARDWARE_EVENT
title: _URS_HARDWARE_EVENT (urstypes.h)
description: Defines values for the hardware events that a client driver for a USB dual-role controller can report.
old-location: buses\urs_hardware_event.htm
tech.root: usbref
ms.assetid: 985A7725-1EE1-4419-B8BE-FEE2306E93A7
ms.date: 05/07/2018
keywords: ["_URS_HARDWARE_EVENT enumeration"]
ms.keywords: "*PURS_HARDWARE_EVENT, URS_HARDWARE_EVENT, URS_HARDWARE_EVENT enumeration [Buses], URS_HARDWARE_EVENT,*PURS_HARDWARE_EVENT, URS_HARDWARE_EVENT,*PURS_HARDWARE_EVENT enumeration [Buses], UrsHardwareEventDetach, UrsHardwareEventIdFloat, UrsHardwareEventIdGround, UrsHardwareEventNone, UrsHardwareEventPortTypeDfp, UrsHardwareEventPortTypeUfp, _URS_HARDWARE_EVENT, buses.urs_hardware_event, urstypes/URS_HARDWARE_EVENT, urstypes/UrsHardwareEventDetach, urstypes/UrsHardwareEventIdFloat, urstypes/UrsHardwareEventIdGround, urstypes/UrsHardwareEventNone, urstypes/UrsHardwareEventPortTypeDfp, urstypes/UrsHardwareEventPortTypeUfp"
f1_keywords:
 - "urstypes/URS_HARDWARE_EVENT, *PURS_HARDWARE_EVENT"
req.header: urstypes.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
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
- Urstypes.h
api_name:
- URS_HARDWARE_EVENT, *PURS_HARDWARE_EVENT
product:
- Windows
targetos: Windows
req.typenames: URS_HARDWARE_EVENT, *PURS_HARDWARE_EVENT
---

# _URS_HARDWARE_EVENT enumeration


## -description


Defines values for the hardware events that a client driver for a USB dual-role controller can report.


## -enum-fields




### -field UrsHardwareEventNone

Internal use only. 


### -field UrsHardwareEventDetach

A detach event occurred on a port of a USB Type-C system. 


### -field UrsHardwareEventIdGround

This event indicates that the ID pin is grounded.


### -field UrsHardwareEventIdFloat

This event indicates that the ID pin is floating.


### -field UrsHardwareEventPortTypeDfp

The Type-C connector has resolved to DFP. Not to be used directly by the URS client driver.


### -field UrsHardwareEventPortTypeUfp

The Type-C connector has resolved to UFP. Not to be used directly by the URS client driver.


## -remarks



Values defined for USB Type-C systems should not be directly used by the client driver. Instead the driver should report that it does not support hardware event reporting by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ursdevice/nf-ursdevice-urssethardwareeventsupport">UrsSetHardwareEventSupport</a>. These hardware events are detected by a USB Type-C connector driver, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmmanager/">USB Type-C connector driver programming reference</a>. 



