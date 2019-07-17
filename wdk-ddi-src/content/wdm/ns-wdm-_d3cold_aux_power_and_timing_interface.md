---
UID: NS:wdm._D3COLD_AUX_POWER_AND_TIMING_INTERFACE
title: _D3COLD_AUX_POWER_AND_TIMING_INTERFACE (wdm.h)
description: Allows device drivers to negotiate a higher auxiliary power for their PCI devices while in D3Cold state. 
ms.assetid: a69dbe9e-ea7d-4b71-8fa8-eb92abb3447b
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "wdm/_D3COLD_AUX_POWER_AND_TIMING_INTERFACE"
ms.keywords: _D3COLD_AUX_POWER_AND_TIMING_INTERFACE, *PD3COLD_AUX_POWER_AND_TIMING_INTERFACE, D3COLD_AUX_POWER_AND_TIMING_INTERFACE, 
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3COLD_AUX_POWER_AND_TIMING_INTERFACE, *PD3COLD_AUX_POWER_AND_TIMING_INTERFACE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- wdm.h
api_name: 
- _D3COLD_AUX_POWER_AND_TIMING_INTERFACE
product:
- Windows
targetos: Windows
---

# _D3COLD_AUX_POWER_AND_TIMING_INTERFACE structure

## -description
An extended version of the INTERFACE structure that allows device drivers to negotiate a higher auxiliary power for their PCI devices while in D3Cold state. This interface allows device drivers to invoke the functions that manipulate _DSM functions 0Ah, 0Bh.

## -struct-fields

### -field Size
The size, in bytes, of this structure.

### -field Version
The driver-defined interface version. The current version of this interface is D3COLD_AUX_POWER_AND_TIMING_INTERFACE_VERSION.
 
### -field Context
A pointer to interface-specific context information.
 
### -field InterfaceReference
A pointer to an [InterfaceReference](nc-wdm-pinterface_reference.md) routine that increments the interface's reference count. 
 
### -field InterfaceDereference
A pointer to an [InterfaceDereference]nc-wdm-pinterface_dereference.md) routine that decrements the interface's reference count.
 
### -field RequestCorePowerRail
A pointer to a [_D3COLD_REQUEST_CORE_POWER_RAIL_](nc-wdm-d3cold_request_core_power_rail.md) callback function that enables the function device object (FDO) to indicate whether the core power rail is needed.

### -field RequestAuxPower
A pointer to a [_D3COLD_REQUEST_AUX_POWER](nc-wdm-d3cold_request_aux_power.md) callback function that enables the function device object (FDO) to convey its auxiliary power requirement.
 
### -field RequestPerstDelay
A pointer to a [_D3COLD_REQUEST_PERST_DELAY_](nc-wdm-d3cold_request_perst_delay.md) enables the function device object (FDO) to convey its requirement for a fixed delay time.

## -remarks
A device driver that successfully queries for the GUID_D3COLD_AUX_POWER_AND_TIMING_INTERFACE interface receives a pointer to a [**D3COLD_AUX_POWER_AND_TIMING_INTERFACE**] structure in which the pointers to the routines in the interface are all non-NULL and valid. 

The [**D3COLD_AUX_POWER_AND_TIMING_INTERFACE**] structure is an extended version of the [INTERFACE] structure.

Windows now has added support for the newly introduced [PCI Device Specific Method (_DSM) functions for Runtime Device Power Management](https://pcisig.com/sites/default/files/specification_documents/ECN_D3ColdTiming_Power_Firmware_Final.pdf). The new interfaces listed below allow device drivers to negotiate a higher auxiliary power for their PCI devices (higher than the standard 375mA @ 3.3V), if their devices require additional power while in D3Cold state. All device drivers must be able to handle the cases where additional power cannot be provided by the system, or if the interfaces are not supported.

## -see-also
[_D3COLD_REQUEST_CORE_POWER_RAIL_](nc-wdm-d3cold_request_core_power_rail.md)

[_D3COLD_REQUEST_AUX_POWER](nc-wdm-d3cold_request_aux_power.md)

[_D3COLD_REQUEST_PERST_DELAY_](nc-wdm-d3cold_request_perst_delay.md)
