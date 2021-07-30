---
UID: NC:wdm.GET_VIRTUAL_FUNCTION_PROBED_BARS
title: GET_VIRTUAL_FUNCTION_PROBED_BARS (wdm.h)
description: The GetVirtualFunctionProbedBars routine returns the values of the PCI Express (PCIe) Base Address Registers (BARs) of a device that supports the single root I/O virtualization (SR-IOV) interface.
old-location: pci\getvirtualfunctionprobedbars.htm
tech.root: PCI
ms.date: 07/29/2021
keywords: ["GET_VIRTUAL_FUNCTION_PROBED_BARS callback"]
ms.keywords: GET_VIRTUAL_FUNCTION_PROBED_BARS, GetVirtualFunctionProbedBars, GetVirtualFunctionProbedBars routine, PCI.getvirtualfunctionprobedbars, wdm/GetVirtualFunctionProbedBars
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2012 and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
f1_keywords:
 - GET_VIRTUAL_FUNCTION_PROBED_BARS
 - wdm/GET_VIRTUAL_FUNCTION_PROBED_BARS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - GET_VIRTUAL_FUNCTION_PROBED_BARS
---

# GET_VIRTUAL_FUNCTION_PROBED_BARS callback

## -description

The [GetVirtualFunctionProbedBars](/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_function_probed_bars) routine returns the values of the PCI Express (PCIe) Base Address Registers (BARs) of a device that supports the single root I/O virtualization (SR-IOV) interface.

[GetVirtualFunctionProbedBars](/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_function_probed_bars) returns the BAR values that were reported by the device after a query that was performed by the PCI bus driver. This query determines the memory or I/O address space that is required by the device.

## -parameters

### -param Context

[in, out] A pointer to interface-specific context information. The caller passes the value that is passed as the **Context** member of the [PCI_VIRTUALIZATION_INTERFACE](/previous-versions/windows/hardware/drivers/hh406642(v=vs.85)) structure for the interface.

### -param BaseRegisterValues

[out] A pointer to an array of ULONG values. The [GetVirtualFunctionProbedBars](/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_function_probed_bars) routine returns a value for each BAR of the device.

> [!NOTE]
> [GetVirtualFunctionProbedBars](/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_function_probed_bars) returns a maximum of **PCI_TYPE0_ADDRESSES** values within this array.

## -returns

The [GetVirtualFunctionProbedBars](/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_function_probed_bars) routine returns one of the following NTSTATUS values:

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | The operation completed successfully. |
| **STATUS_INVALID_DEVICE_STATE** | The device does not support the SR-IOV interface. |

## -prototype

```cpp
GET_VIRTUAL_FUNCTION_PROBED_BARS GetVirtualFunctionProbedBars;

NTSTATUS GetVirtualFunctionProbedBars(
  _Inout_ PVOID  Context,
  _Out_   PULONG BaseRegisterValues
)
{ ... }
```

## -remarks

The PCI bus driver. which runs in the management operating system  of the Hyper-V parent partition, queries the memory or I/O address space requirements of each  BAR of the device. The PCI bus driver performs this query when the it first detects the adapter on the bus.

Through this BAR query, the PCI bus driver determines the following:

- Whether a BAR is supported by the device.

- If a BAR is supported, how much memory or I/O address space is required for the BAR.

The PCI driver performs this BAR query as follows:

1. The PCI bus driver writes 0xFFFFFFFF to a BAR.

1. The PCI bus driver reads the BAR to determine the memory or address space that the device requires. A value of zero indicates that the device does not support the BAR.

The [GetVirtualFunctionProbedBars](/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_function_probed_bars) routine is provided by the **GUID_PCI_VIRTUALIZATION_INTERFACE** interface.

The following notes apply to the [GetVirtualFunctionProbedBars](/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_function_probed_bars) routine:

- The SR-IOV interface does not require that the BARs of a PCIe VF comply with the protocol for determining the size of the memory block or I/O address space of a BAR. Therefore, the virtual PCI (VPCI) driver, which runs in the guest operating system, determines the size by using the equivalent size from the BARs on the physical device. The VPCI driver obtains this information by calling the [GetVirtualFunctionProbedBars](/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_function_probed_bars) routine.

- The VPCI driver requires the size of the memory or I/O
address space for each BAR after the physical device has started. At that point, the PCI driver cannot perform a BAR query  on the device without altering the current value of the BAR. Therefore, when the [GetVirtualFunctionProbedBars](/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_function_probed_bars) routine is called by the VPCI driver, the PCI driver returns the BAR information that it obtained during the BAR query. The PCI driver performed this query when the device was first detected on the bus.

## -see-also

[PCI_VIRTUALIZATION_INTERFACE](/previous-versions/windows/hardware/drivers/hh406642(v=vs.85))
