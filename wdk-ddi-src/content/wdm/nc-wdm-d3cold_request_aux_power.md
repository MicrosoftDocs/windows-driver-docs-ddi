---
UID: NC:wdm.D3COLD_REQUEST_AUX_POWER
title: D3COLD_REQUEST_AUX_POWER (wdm.h)
description: Enables the function device object (FDO) to convey its auxiliary power requirement.
ms.assetid: c367131f-520b-4d5a-8ccd-e465057cf102
ms.date: 10/19/2018
tech.root: kernel
keywords: ["D3COLD_REQUEST_AUX_POWER callback function"]
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
targetos: Windows
f1_keywords:
 - D3COLD_REQUEST_AUX_POWER
 - wdm/D3COLD_REQUEST_AUX_POWER
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - D3COLD_REQUEST_AUX_POWER
---

# D3COLD_REQUEST_AUX_POWER callback function


## -description

Enables the function device object (FDO) to convey its auxiliary power requirement.

## -parameters

### -param Context

[_In_reads_opt_(_Inexpressible_("varies"))] The handle to the device.

### -param AuxPowerInMilliWatts

[_In_] The wattage in units of mW that the device needs for D3cold when the system is in S0. This value must be less than 0x80000000.

### -param RetryInSeconds 

[_Out_] A pointer to a ULONG variable that receives the number of seconds the driver can retry its request when the request fails with STATUS_RETRY.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values). Possible errors are as follows:

| Error code                    | Description                                                                                                                                                                       |
| ----------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| STATUS_INVALID_PARAMETER      |The input parameter is not valid.                                                                                                                                              |
| STATUS_INVALID_DEVICE_REQUEST | The device is not in D0 or not the requester is not Function 0.                                                                                                                |
| STATUS_RETRY                  | The request failed and the system indicates that a retry can be made. RetryInSeconds will contain the number of seconds the driver should wait before making the next request. |
| STATUS_UNSUCCESSFUL           | The request failed and the system indicates that the current requested value is not possible.                                                                                  |
| STATUS_SUCCESS                | The request succeedeed.                                                                                                                                                          |

## -prototype

```cpp
//Declaration

D3COLD_REQUEST_AUX_POWER D3coldRequestAuxPower; 

// Definition

NTSTATUS D3coldRequestAuxPower 
(
	PVOID Context
	ULONG AuxPowerInMilliWatts
	PULONG RetryInSeconds
)
{...}

D3COLD_REQUEST_AUX_POWER *PD3COLD_REQUEST_AUX_POWER


```

## -remarks

A device driver that successfully queries for the GUID_D3COLD_AUX_POWER_AND_TIMING_INTERFACE interface receives a pointer to a [**D3COLD_AUX_POWER_AND_TIMING_INTERFACE**](ns-wdm-_d3cold_aux_power_and_timing_interface.md) structure in which the driver sets the **RequestAuxPower** member to a pointer to its implementation of the _D3COLD_REQUEST_AUX_POWER_ callback function.

  - For a multi-function device, only Function 0 is expected to call this
    routine and set the auxiliary power for the entire device.

  - Function 0 must be in D0 state when this routine is called.

  - There is no guarantee that the core power rail power will be removed after the 
    success of this request.

## -see-also
