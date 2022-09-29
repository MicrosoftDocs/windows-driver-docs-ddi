---
UID: NC:vpci.VPCI_READ_BLOCK
tech.root: pci
title: VPCI_READ_BLOCK
ms.date: 09/29/2022
targetos: Windows
description: Learn more about the VPCI_READ_BLOCK routine
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: vpci.h
req.idl: 
req.include-header: 
req.irql: <= APC_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2012
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - vpci.h
api_name:
 - VPCI_READ_BLOCK
f1_keywords:
 - VPCI_READ_BLOCK
 - vpci/VPCI_READ_BLOCK
dev_langs:
 - c++
helpviewer_keywords:
 - VPCI_READ_BLOCK
---

## -description

The *ReadVfConfigBlock* routine reads a block of configuration data for a PCI Express (PCIe) virtual function (VF). This routine is called by the driver of a PCIe VF on a device that supports the single root I/O virtualization (SR-IOV) interface.

## -parameters

### -param Context

[in] A pointer to interface-specific context information. The caller passes the value that is passed as the **Context** member of the [**VPCI\_INTERFACE\_STANDARD**](ns-vpci-vpci_interface_standard.md) structure for the interface.

### -param BlockId

[in] The identifier of the VF configuration block to be read. This identifier is proprietary to the independent hardware vendor (IHV) and is used only by the drivers for the PCIe physical function (PF) and VF on the device.

### -param Buffer

[out] A pointer to a caller-allocated buffer that will contain the configuration data to be read. For more information, see Remarks.

### -param Length

[in] The number of bytes to be read from the VF configuration block.

> [!NOTE]
> The value of this parameter must not exceed **VPCI\_MAX\_READ\_WRITE\_BLOCK\_SIZE**.

## -returns

The *ReadVfConfigBlock* routine returns **STATUS\_SUCCESS** if the operation succeeds. Otherwise, the routine returns an appropriate NTSTATUS value.

## -remarks

When the *ReadVfConfigBlock* routine is called, the driver of the PF is notified to return data from a specified VF configuration block.

A VF configuration block is used for backchannel communication between the drivers of the PF and a VF on a device that supports the SR-IOV interface. The IHV can define one or more VF configuration blocks for the device. Each VF configuration block has an IHV-defined format, length, and block ID.

VF configuration data can be exchanged between the following drivers in a protected manner:

- The VF driver, which runs in the guest operating system. This operating system runs within a Hyper-V child partition.
- The PF driver, which runs in the management operating system. This operating system runs within the Hyper-V parent partition.

Data from each VF configuration block is used only by the drivers of the PF and VF.

> [!NOTE]
> The [**IOCTL\_VPCI\_READ\_BLOCK**](ni-vpci-ioctl_vpci_read_block.md) IOCTL offers an asynchronous alternative to the *ReadVfConfigBlock* routine.

## -see-also

[**IOCTL\_VPCI\_READ\_BLOCK**](ni-vpci-ioctl_vpci_read_block.md)

[**VPCI\_INTERFACE\_STANDARD**](ns-vpci-vpci_interface_standard.md)
