---
UID: NC:wdm.ENABLE_VIRTUALIZATION
title: ENABLE_VIRTUALIZATION (wdm.h)
description: The EnableVirtualization routine enables or disables virtualization for a PCI Express (PCIe) device that supports the single root I/O virtualization (SR-IOV) interface.
old-location: pci\enablevirtualization.htm
tech.root: PCI
ms.date: 07/29/2021
keywords: ["ENABLE_VIRTUALIZATION callback"]
ms.keywords: ENABLE_VIRTUALIZATION, EnableVirtualization, EnableVirtualization routine, PCI.enablevirtualization, wdm/EnableVirtualization
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
f1_keywords:
 - ENABLE_VIRTUALIZATION
 - wdm/ENABLE_VIRTUALIZATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - ENABLE_VIRTUALIZATION
---

# ENABLE_VIRTUALIZATION callback

## -description

The [EnableVirtualization]() routine enables or disables virtualization for a PCI Express (PCIe) device that supports the single root I/O virtualization (SR-IOV) interface.

## -parameters

### -param Context [in, out]

A pointer to interface-specific context information. The caller passes the value that is passed as the **Context** member of the [PCI_VIRTUALIZATION_INTERFACE](/previous-versions/windows/hardware/drivers/hh406642(v=vs.85)) structure for the interface.

### -param NumVFs [in]

The number of PCIe virtual functions (VFs) that are to be enabled for the device. The [EnableVirtualization]() routine sets the **NumVFs** member of the PCIe SR-IOV Extended Capability structure to the value of the *NumVFs* parameter.

> [!NOTE]
> If the *EnableVirtualization* parameter is **FALSE**, the *NumVFs* parameter must be set to zero.

### -param EnableVfMigration [in]

A BOOLEAN value that indicates whether the multi-root I/O virtualization (MR-IOV) base function (BF) can dynamically reprovision the PCIe physical function (PF) of the device   as a VF at run time.

> [!NOTE]
> This parameter is only applicable to devices that support both the SR-IOV and MR-IOV interfaces. The driver must set this parameter to **FALSE** if the device supports only the SR-IOV interface and not the MR-IOV interface.

### -param EnableMigrationInterrupt [in]

A BOOLEAN value that indicates whether the interrupt associated with the PF should be masked or unmasked during VF migration.

> [!NOTE]
> If the *EnableVfMigration* parameters is **FALSE**, the driver must also set this parameter to **FALSE**.

### -param EnableVirtualization [in]

A BOOLEAN value that indicates whether virtualization is enabled on the PCIe configuration space of the device. If the *EnableVirtualization* parameter is **TRUE**, the [EnableVirtualization]() routine sets the VF Enable bit of the PCIe SR-IOV Control field. The *EnableVirtualization* routine clears this bit if the *EnableVirtualization* parameter is **FALSE**.

## -returns

The [EnableVirtualization]() routine returns one of the following NTSTATUS values:

|Return code  |Description  |
|---------|---------|
|**STATUS_SUCCESS**     |     The operation completed successfully.    |
|**STATUS_INVALID_PARAMETER**     |     The *NumVFs* parameter is either zero or  is larger than the value of the **TotalVFs** member of the SR-IOV Extended Capability structure for the device.    |
|**STATUS_INVALID_DEVICE_STATE**     |    Virtualization is already enabled on the device and the *EnableVirtualization* parameter is **TRUE**, or virtualization is already disabled on the device and the *EnableVirtualization* parameter is **FALSE**.     |

## -prototype

```cpp
ENABLE_VIRTUALIZATION EnableVirtualization;

NTSTATUS EnableVirtualization(
  _Inout_ PVOID   Context,
  _In_    UINT16  NumVFs,
  _In_    BOOLEAN EnableVfMigration,
  _In_    BOOLEAN EnableMigrationInterrupt,
  _In_    BOOLEAN EnableVirtualization
)
{ ... }
```

## -remarks

Drivers call the [EnableVirtualization]() routine to configure the SR-IOV Extended Capability fields in the PCIe configuration space. This call enables or disables virtualization in the configuration space, and specifies the number of VFs that should be exposed to the PCIe fabric by the device.

The [EnableVirtualization]() routine is provided by the **GUID_PCI_VIRTUALIZATION_INTERFACE** interface.

## -see-also

[PCI_VIRTUALIZATION_INTERFACE](/previous-versions/windows/hardware/drivers/hh406642(v=vs.85))
