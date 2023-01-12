---
UID: NS:d3dkmddi._DXGK_PHYSICALADAPTERCAPS
title: DXGK_PHYSICALADAPTERCAPS (d3dkmddi.h)
description: The DXGK_PHYSICALADAPTERCAPS structure is used to report details of a physical adapter.
old-location: display\dxgk_physicaladaptercaps.htm
ms.date: 08/24/2022
keywords: ["DXGK_PHYSICALADAPTERCAPS structure"]
ms.keywords: DXGK_PHYSICALADAPTERCAPS, DXGK_PHYSICALADAPTERCAPS structure [Display Devices], Flags.GpuMmuSupported, Flags.IoMmuSupported, Flags.MovePagingSupported, Flags.VPRPagingContextRequired, _DXGK_PHYSICALADAPTERCAPS, d3dkmddi/DXGK_PHYSICALADAPTERCAPS, display.dxgk_physicaladaptercaps
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: DXGK_PHYSICALADAPTERCAPS
f1_keywords:
 - _DXGK_PHYSICALADAPTERCAPS
 - d3dkmddi/_DXGK_PHYSICALADAPTERCAPS
 - DXGK_PHYSICALADAPTERCAPS
 - d3dkmddi/DXGK_PHYSICALADAPTERCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_PHYSICALADAPTERCAPS
 - DXGK_PHYSICALADAPTERCAPS
---

# DXGK_PHYSICALADAPTERCAPS structure

## -description

The **DXGK_PHYSICALADAPTERCAPS** structure is used to report details of a physical adapter.

## -struct-fields

### -field NumExecutionNodes

The number of execution nodes in the physical adapter.

### -field PagingNodeIndex

Index of the paging node for the physical adapter.

### -field DxgkPhysicalAdapterHandle

Handle, which is passed to the kernel mode driver as **DXGKRNL_INTERFACE::DeviceHandle** in [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md).

### -field Flags

|Value|Meaning|
|--- |--- |
|Flags.IoMmuSupported TRUE|The adapter supports IoMmu.|
|Flags.GpuMmuSupported TRUE|The adapter supports GpuMmu.|
|Flags.MovePagingSupported TRUE|The adapter supports move paging.|
|Flags.VPRPagingContextRequired TRUE|The adapter requires the index of the VPR paging node.|

### -field VPRPagingNode

Index of the node to be used for move paging in the VPR.

### -field VirtualCopyNodeIndex

Node is specified as a virtual copy engine node. Available starting in Windows 10 version 2004 (WDDM 2.7).
