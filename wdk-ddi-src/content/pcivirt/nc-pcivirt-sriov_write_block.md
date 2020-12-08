---
UID: NC:pcivirt.SRIOV_WRITE_BLOCK
title: SRIOV_WRITE_BLOCK (pcivirt.h)
description: Writes data to the specified configuration block of a PCI Express SR-IOV Virtual Function (VF).
old-location: pci\sriov_write_block.htm
tech.root: PCI
ms.date: 02/24/2018
keywords: ["SRIOV_WRITE_BLOCK callback"]
ms.keywords: "*PSRIOV_WRITE_BLOCK, *PSRIOV_WRITE_BLOCK callback function pointer [Buses], PCI.sriov_write_block, SRIOV_WRITE_BLOCK, SriovWriteBlock, SriovWriteBlock callback function [Buses], pcivirt/SriovWriteBlock"
req.header: pcivirt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
f1_keywords:
 - SRIOV_WRITE_BLOCK
 - pcivirt/SRIOV_WRITE_BLOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Pcivirt.h
api_name:
 - PSRIOV_WRITE_BLOCK
---

# SRIOV_WRITE_BLOCK callback


## -description

Writes data to the specified configuration block of a PCI Express SR-IOV Virtual Function (VF).

## -parameters

### -param Context 

[in]
A pointer to a driver-defined context.

### -param VfIndex 

[in]
A zero-based index of the VF to which this write operation applies.

### -param BlockId 

[in]
A number identifying the block to be written.  This is defined by the provider of the PF driver.

### -param Buffer 

[in]
A pointer to a buffer that contains the data to write to the VF's  configuration space.

### -param Length

The length in bytes of this write operation.  Must not be greater than VPCI_MAX_READ_WRITE_BLOCK_SIZE defined in Pcivirt.h.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.

## -prototype

```cpp
SRIOV_WRITE_BLOCK SriovWriteBlock;

NTSTATUS SriovWriteBlock(
  _In_ PVOID  Context,
  _In_ USHORT VfIndex,
  _In_ ULONG  BlockId,
  _In_ PVOID  Buffer,
       ULONG  Length
)
{ ... }

typedef SRIOV_WRITE_BLOCK *PSRIOV_WRITE_BLOCK;
```

## -remarks

This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to read a configuration block for one of its VFs.

The PF driver registers its implementation by setting the <b>WriteVfConfigBlock</b> member of the <a href="/windows-hardware/drivers/ddi/pcivirt/ns-pcivirt-_sriov_device_interface_standard">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.
