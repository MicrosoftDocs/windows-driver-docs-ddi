---
UID: NC:wdm.D3COLD_REQUEST_CORE_POWER_RAIL
title: D3COLD_REQUEST_CORE_POWER_RAIL (wdm.h)
description: Enables the function device object (FDO) to indicate whether the core power rail is needed.
ms.assetid: 48ce96cc-8827-47ba-bb32-028b0744c58e
ms.date: 10/19/2018
ms.topic: callback
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- UserDefined
api_location:
- wdm.h
api_name: 
- D3COLD_REQUEST_CORE_POWER_RAIL
product:
- Windows
targetos: Windows
---

# D3COLD_REQUEST_CORE_POWER_RAIL callback function

## -description

Enables the function device object (FDO) to indicate whether the core power rail is needed.


## -prototype

```cpp
//Declaration

D3COLD_REQUEST_CORE_POWER_RAIL D3coldRequestCorePowerRail; 

// Definition

VOID D3coldRequestCorePowerRail 
(
	PVOID Context
	BOOLEAN CorePowerRailNeeded
)
{...}

D3COLD_REQUEST_CORE_POWER_RAIL *PD3COLD_REQUEST_CORE_POWER_RAIL


```

## -parameters

### -param Context
[_In_reads_opt_(_Inexpressible_("varies"))] The handle to the device.
 
### -param CorePowerRailNeeded: 
[_In_] A flag that indicates whether or not the driver needs the core power rail.


## -returns

## -remarks
A device driver that successfully queries for the GUID_D3COLD_AUX_POWER_AND_TIMING_INTERFACE interface receives a pointer to a [**D3COLD_AUX_POWER_AND_TIMING_INTERFACE**](ns-wdm-_d3cold_aux_power_and_timing_interface.md) structure in which the driver sets the **RequestCorePowerRail** member to a pointer to its implementation of the _D3COLD_REQUEST_CORE_POWER_RAIL_ callback function.

  - If the driver indicates that the core power rail is needed, it is
    guaranteed that the core power rail is turned on when this call returns.

  - When a driver indicates that the core power rail is no longer needed,
    there is no guarantee of the core power rail state onwards.

  - This routine can never fail. 


## -see-also
