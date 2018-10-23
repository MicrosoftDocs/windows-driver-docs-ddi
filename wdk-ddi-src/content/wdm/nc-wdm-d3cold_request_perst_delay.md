---
UID: NC:wdm.D3COLD_REQUEST_PERST_DELAY
title: D3COLD_REQUEST_PERST_DELAY
author: windows-driver-content
description: Enables the function device object (FDO) to convey its requirement for a fixed delay time. 
ms.assetid: c81274ad-e9e9-4ad2-a6e0-fac03e792071
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
topictype: 
-	apiref
apitype: 
-	UserDefined
apilocation: 
-	wdm.h
apiname: 
-	D3COLD_REQUEST_PERST_DELAY
product:
-	Windows
targetos: Windows
---

# D3COLD_REQUEST_PERST_DELAY callback function

## -description

Enables the function device object (FDO) to convey its requirement for a fixed delay time between the PME_TO_Ack message is received at the PCI Express Downstream Port that originated the PME_Turn_Off message, and the time the platform asserts PERST# to the slot during the corresponding endpoint’s or PCI Express Upstream Port’s transition to D3cold while the system is in an ACPI operational state.
 

## -prototype

```cpp
//Declaration

D3COLD_REQUEST_PERST_DELAY D3coldRequestPerstDelay; 

// Definition

NTSTATUS D3coldRequestPerstDelay 
(
	PVOID Context
	ULONG DelayInMicroSeconds
)
{...}

D3COLD_REQUEST_PERST_DELAY *PD3COLD_REQUEST_PERST_DELAY


```

## -parameters

### -param Context 
[_In_reads_opt_(_Inexpressible_("varies"))] The handle to the device.

### -param DelayInMicroSeconds
[_In_] The delay in units of microsecond. The maximum value is 10000 microseconds.


## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks
A device driver that successfully queries for the GUID_D3COLD_AUX_POWER_AND_TIMING_INTERFACE interface receives a pointer to a [**D3COLD_AUX_POWER_AND_TIMING_INTERFACE**](ns-wdm-_d3cold_aux_power_and_timing_interface.md) structure in which the driver sets the **RequestPerstDelay** member to a pointer to its implementation of the _D3COLD_REQUEST_PERST_DELAY_ callback function.

  - For a multi-function device, only Function 0 is allowed to call this
    routine.

  - Function 0 must be in D0 when calling this routine.



## -see-also
