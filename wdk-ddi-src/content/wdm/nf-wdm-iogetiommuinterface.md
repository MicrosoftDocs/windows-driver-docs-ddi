---
UID: NF:wdm.IoGetIommuInterface
title: IoGetIommuInterface function (wdm.h)
description: Retrieves a pointer to the interface that contains pointers to IOMMU routines.
ms.assetid: 2b69dea5-3c7d-4bf8-a657-893749fbf23c
ms.date: 10/19/2018
keywords: ["IoGetIommuInterface function"]
f1_keywords:
 - "wdm/IoGetIommuInterface"
 - "IoGetIommuInterface"
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
topic_type: 
- apiref
api_type: 
- DllExport
api_location:
- NtosKrnl.exe
api_name: 
- IoGetIommuInterface
product:
- Windows
targetos: Windows

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
