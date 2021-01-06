---
UID: NC:wdm.FPGA_CONTROL_LINK
title: FPGA_CONTROL_LINK (wdm.h)
description: Reserved for future use.
ms.date: 10/19/2018
tech.root: kernel
keywords: ["FPGA_CONTROL_LINK callback function"]
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - FPGA_CONTROL_LINK
 - wdm/FPGA_CONTROL_LINK
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - FPGA_CONTROL_LINK
---

# FPGA_CONTROL_LINK callback function


## -description

Reserved for future use.
Enables or disables the link between the given FPGA device and its parent bridge.

## -parameters

### -param Context

[_In_reads_opt_(_Inexpressible_("varies"))] The handle to the bus extension.

### -param Enable

[_In_] A boolean value that indicates whether the link should be enabled or disabled. TRUE indicates enabled; FALSE otherwise.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -prototype

```cpp
//Declaration

FPGA_CONTROL_LINK FpgaControlLink;

// Definition

NTSTATUS FpgaControlLink 
(
	PVOID Context
	BOOLEAN Enable
)
{...}

FPGA_CONTROL_LINK *PFPGA_CONTROL_LINK


```

## -remarks

A device driver that successfully queries for the GUID_PCI_FPGA_CONTROL_INTERFACE interface receives a pointer to a [**FPGA_CONTROL_INTERFACE**](ns-wdm-_fpga_control_interface.md) structure in which the driver sets the **ControlLink** member to a pointer to its implementation of the _FPGA_CONTROL_CONFIG_SPACE_ callback function.

## -see-also
