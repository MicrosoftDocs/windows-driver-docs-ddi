---
UID: NC:wdm.FPGA_CONTROL_ERROR_REPORTING
title: FPGA_CONTROL_ERROR_REPORTING (wdm.h)
description: Reserved for future use. Toggles the error reporting for the FPGA device and its parent bridge.
ms.assetid: b7e4aaab-52a9-4d9d-892b-6f02f1172127
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "wdm/FPGA_CONTROL_ERROR_REPORTING"
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
topic_type: 
- apiref
api_type: 
- UserDefined
api_location:
- wdm.h
api_name: 
- FPGA_CONTROL_ERROR_REPORTING
product:
- Windows
targetos: Windows
---

# FPGA_CONTROL_ERROR_REPORTING callback function

## -description

Reserved for future use.
Toggles the error reporting for the FPGA device and its parent bridge.
 

## -prototype

```cpp
//Declaration

FPGA_CONTROL_ERROR_REPORTING FpgaControlErrorReporting; 

// Definition

NTSTATUS FpgaControlErrorReporting 
(
	PVOID Context
	ULONG UncorrectableMask
	ULONG CorrectableMask
	BOOLEAN DisableErrorReporting
)
{...}

FPGA_CONTROL_ERROR_REPORTING *PFPGA_CONTROL_ERROR_REPORTING


```

## -parameters

### -param Context
[_In_reads_opt_(_Inexpressible_("varies"))] The handle to the bus extension.
 
### -param UncorrectableMask
[_In_] A bitwise mask of flags defined in [**PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_pci_express_uncorrectable_error_mask) that indicates the uncorrectable masks to be toggled.
 
### -param CorrectableMask
[_In_]  A bitwise mask of flags defined in [**PCI_EXPRESS_CORRECTABLE_ERROR_MASK**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_pci_express_correctable_error_mask) that indicates the correctable masks to be toggled.

### -param DisableErrorReporting
[_In_] A flag indicates whether the error reporting is being disabled or enabled.


## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

A device driver that successfully queries for the GUID_PCI_FPGA_CONTROL_INTERFACE interface receives a pointer to a [**FPGA_CONTROL_INTERFACE**](ns-wdm-_fpga_control_interface.md) structure in which the driver sets the **ControlErrorReporting** member to a pointer to its implementation of the _FPGA_CONTROL_CONFIG_SPACE_ callback function.

- This callback function expects that the FPGA device is in D0 state and its configuration space has not been locked.

- When _DisableErrorReporting_ is set to TRUE, each set bit in the given masks is set in the AER capability of the FPGA device. When _DisableErrorReporting_ is set to FALSE, the original AER masks will be restored.


## -see-also
