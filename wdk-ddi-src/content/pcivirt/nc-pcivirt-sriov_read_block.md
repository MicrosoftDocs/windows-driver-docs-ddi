---
UID: NC:pcivirt.SRIOV_READ_BLOCK
title: SRIOV_READ_BLOCK (pcivirt.h)
description: Reads data from the specified configuration block of a PCI Express SR-IOV Virtual Function (VF).
old-location: pci\sriov_read_block.htm
tech.root: PCI
ms.date: 02/24/2018
keywords: ["SRIOV_READ_BLOCK callback"]
ms.keywords: "*PSRIOV_READ_BLOCK, *PSRIOV_READ_BLOCK callback function pointer [Buses], PCI.sriov_read_block, SRIOV_READ_BLOCK, SriovReadBlock, SriovReadBlock callback function [Buses], pcivirt/SriovReadBlock"
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
 - SRIOV_READ_BLOCK
 - pcivirt/SRIOV_READ_BLOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Pcivirt.h
api_name:
 - SRIOV_READ_BLOCK
---

# SRIOV_READ_BLOCK callback


## -description

Reads data from the specified configuration block of a PCI Express SR-IOV Virtual Function (VF).

## -parameters

### -param Context [in]


A pointer to a driver-defined context.

### -param VfIndex [in]


A zero-based index of the VF to which this read operation applies.

### -param BlockId [in]


A number identifying the block to be read.  This is defined by the provider of the PF driver.

### -param Buffer [out]


A pointer to a buffer that receives the data read from the VF's  configuration space.

### -param Length [in]


The length in bytes of this read operation.  Must not be greater than VPCI_MAX_READ_WRITE_BLOCK_SIZE defined in Pcivirt.h.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.

## -prototype

```cpp
SRIOV_READ_BLOCK SriovReadBlock;

NTSTATUS SriovReadBlock(
  _In_  PVOID  Context,
  _In_  USHORT VfIndex,
  _In_  ULONG  BlockId,
  _Out_ PVOID  Buffer,
  _In_  ULONG  Length
)
{ ... }

typedef SRIOV_READ_BLOCK *PSRIOV_READ_BLOCK;
```

## -remarks

This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to read a configuration block for one of its VFs.

The PF driver registers its implementation by setting the <b>ReadVfConfigBlock</b> member of the <a href="/windows-hardware/drivers/ddi/pcivirt/ns-pcivirt-_sriov_device_interface_standard">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.

