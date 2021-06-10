---
UID: NF:wdm.IoGetIommuInterfaceEx
tech.root: kernel
title: IoGetIommuInterfaceEx
ms.date: 06/04/2021
targetos: Windows
description: Retrieves a pointer to the extended interface that contains a set of IOMMU routines.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - IoGetIommuInterfaceEx
f1_keywords:
 - IoGetIommuInterfaceEx
 - wdm/IoGetIommuInterfaceEx
dev_langs:
 - c++
---

## -description

Retrieves a pointer to the extended interface that contains a set of IOMMU routines.

## -parameters

### -param Version

[*In*] The interface version that determines the set of IOMMU routines that are returned.

### -param Flags

[*In*] Configuration flags for the interface. Currently unused.

### -param InterfaceOut

[*Out*] A pointer to a [**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md) structure that contains pointers to IOMMU interface routines for device domain operations.

## -returns

This function returns NTKERNELAPI NTSTATUS.

## -remarks

To use the IOMMU routines provided by the interface, the device driver must be opted into DMA remapping via the [**DmaRemappingCompatible**](/windows-hardware/drivers/pci/enabling-dma-remapping-for-device-drivers) registry key value (set to 1).

This supersedes the deprecated [*IoGetIommuInterface*](nf-wdm-iogetiommuinterface.md) function. Use this Ex one for all versions of IOMMU routines.

## -see-also

[**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md)
