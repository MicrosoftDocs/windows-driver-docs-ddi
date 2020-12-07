---
UID: NF:wdm.IoGetIommuInterface
title: IoGetIommuInterface function (wdm.h)
description: Retrieves a pointer to the interface that contains pointers to IOMMU routines.
tech.root: kernel
ms.date: 10/19/2018
keywords: ["IoGetIommuInterface function"]
ms.keywords: IoGetIommuInterface
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - IoGetIommuInterface
 - wdm/IoGetIommuInterface
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoGetIommuInterface
---

# IoGetIommuInterface function


## -description

Retrieves a pointer to the interface that contains pointers to IOMMU routines.

## -parameters

### -param Version

The interface version.

### -param InterfaceOut

A pointer to a [**DMA_IOMMU_INTERFACE**](ns-wdm-_dma_iommu_interface.md) that contains pointers to IOMMU callback routines for device domain operations.

## -returns

This function returns NTKERNELAPI NTSTATUS.

## -remarks

## -see-also

