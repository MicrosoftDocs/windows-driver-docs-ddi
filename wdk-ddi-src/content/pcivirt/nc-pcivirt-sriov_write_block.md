---
UID: NC:pcivirt.SRIOV_WRITE_BLOCK
title: SRIOV_WRITE_BLOCK
author: windows-driver-content
description: Writes data to the specified configuration block of a PCI Express SR-IOV Virtual Function (VF).
old-location: pci\sriov_write_block.htm
old-project: PCI
ms.assetid: da47d601-2fab-49bb-b669-909a2e5c95c0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSRIOV_WRITE_BLOCK, *PSRIOV_WRITE_BLOCK callback function pointer [Buses], PCI.sriov_write_block, SRIOV_WRITE_BLOCK, SriovWriteBlock, SriovWriteBlock callback function [Buses], pcivirt/SriovWriteBlock"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Pcivirt.h
api_name:
-	*PSRIOV_WRITE_BLOCK
product: Windows
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---

# SRIOV_WRITE_BLOCK callback


## -description


Writes data to the specified configuration block of a PCI Express SR-IOV Virtual Function (VF).


## -prototype


````
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
````


## -parameters




### -param Context [in]

A pointer to a driver-defined context.
                    
                


### -param VfIndex [in]

A zero-based index of the VF to which this write operation applies.


### -param BlockId [in]

A number identifying the block to be written.  This is defined by the provider of the PF driver.


### -param Buffer [in]

A pointer to a buffer that contains the data to write to the VF's  configuration space.


### -param Length

The length in bytes of this write operation.  Must not be greater than VPCI_MAX_READ_WRITE_BLOCK_SIZE defined in Pcivirt.h.


## -returns




Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.




## -remarks



This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to read a configuration block for one of its VFs.

The PF driver registers its implementation by setting the <b>WriteVfConfigBlock</b> member of the <a href="https://msdn.microsoft.com/c71add7d-9920-4b2f-a46a-4a09a94f3900">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.



