---
UID: NC:pcivirt.SRIOV_GET_MMIO_REQUIREMENTS
title: SRIOV_GET_MMIO_REQUIREMENTS
author: windows-driver-content
description: This callback function is not supported.
old-location: pci\sriov_get_mmio_requirements.htm
tech.root: PCI
ms.assetid: e9de3042-35aa-4ffa-ae1e-5135799c9a3b
ms.date: 2/24/2018
ms.keywords: "*PSRIOV_GET_MMIO_REQUIREMENTS, *PSRIOV_GET_MMIO_REQUIREMENTS callback function pointer [Buses], PCI.sriov_get_mmio_requirements, SRIOV_GET_MMIO_REQUIREMENTS, SriovGetMmioRequirements, SriovGetMmioRequirements callback function [Buses], pcivirt/SriovGetMmioRequirements"
ms.topic: callback
req.header: pcivirt.h
req.include-header: Pcivirt.h
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
-	*PSRIOV_GET_MMIO_REQUIREMENTS
product:
- Windows
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---

# SRIOV_GET_MMIO_REQUIREMENTS callback


## -description



This callback function is not supported.

Gets the Memory-Mapped I/O space of the specified PCI Express SR-IOV Virtual Function (VF).


## -prototype


```
SRIOV_GET_MMIO_REQUIREMENTS SriovGetMmioRequirements;

NTSTATUS SriovGetMmioRequirements(
  _In_  PVOID  Context,
  _In_  USHORT VfIndex,
  _In_  ULONG  BlockId,
  _Out_ PVOID  Buffer,
  _In_  ULONG  Length
)
{ ... }

typedef SRIOV_GET_MMIO_REQUIREMENTS *PSRIOV_GET_MMIO_REQUIREMENTS;
```


## -parameters




### -param Context [in]

A pointer to a driver-defined context.




### -param VfIndex [in]

A zero-based index of the VF to which this read operation applies.


### -param BlockId [in]

A number identifying the block to be read.  This is defined by the provider of the PF driver.


### -param Buffer [out]

A pointer to a buffer that receives the data read from the VF's  MMIO space.


### -param Length [in]

The length in bytes of this read operation.


## -returns




Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.





## -remarks



This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to retrieve MMIO requirement of the specified VF.

<code>(Question: How is this registered?)</code>



