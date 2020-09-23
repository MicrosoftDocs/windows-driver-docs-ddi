---
UID: NC:wdm.FPGA_CONTROL_CONFIG_SPACE
title: FPGA_CONTROL_CONFIG_SPACE (wdm.h)
description: Reserved for future use. Enables or disables the access to the configuration space of the FPGA device.
ms.assetid: 963b8836-30f6-4321-9835-3860afe6076d
ms.date: 10/19/2018
keywords: ["FPGA_CONTROL_CONFIG_SPACE callback function"]
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - FPGA_CONTROL_CONFIG_SPACE
 - wdm/FPGA_CONTROL_CONFIG_SPACE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - FPGA_CONTROL_CONFIG_SPACE
---

# FPGA_CONTROL_CONFIG_SPACE callback function


## -description

Reserved for future use.
Enables or disables the access to the configuration space of the FPGA device.

## -parameters

### -param Context

[_In_reads_opt_(_Inexpressible_("varies"))] The handle to the bus extension.

### -param Enable

[_In_] A boolean value that indicates whether the configuration space access should be enabled or disabled. TRUE indicates enabled; FALSE otherwise.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -prototype

```cpp
//Declaration

FPGA_CONTROL_CONFIG_SPACE FpgaControlConfigSpace; 

// Definition

NTSTATUS FpgaControlConfigSpace 
(
	PVOID Context
	BOOLEAN Enable
)
{...}

FPGA_CONTROL_CONFIG_SPACE *PFPGA_CONTROL_CONFIG_SPACE


```

## -remarks

A device driver that successfully queries for the GUID_PCI_FPGA_CONTROL_INTERFACE interface receives a pointer to a [**FPGA_CONTROL_INTERFACE**](ns-wdm-_fpga_control_interface.md) structure in which the driver sets the **ControlConfigSpace** member to a pointer to its implementation of the _FPGA_CONTROL_CONFIG_SPACE_ callback function.

- This callback function toggles the configuration space access to all the functions of the FPGA device.

- When the configuration space is locked down, all read accesses return FF and all write accesses are discarded.

- Until the configuration space is unlocked, the FPGA device is not reported to PNP as missing even when reading its configuration space returns FF.

- If there exists any active bus scan, it is not safe to lock down configuration space as it might confuse the scan bus.

## -see-also