---
UID: NC:dispmprt.DXGKCB_UNMAP_MEMORY
title: DXGKCB_UNMAP_MEMORY (dispmprt.h)
description: The DxgkCbUnmapMemory function unmaps a range of addresses previously mapped by DxgkCbMapMemory.
old-location: display\dxgkcbunmapmemory.htm
tech.root: display
ms.assetid: 71e8eb0e-599b-44cf-955b-828f6667edf6
ms.date: 05/10/2018
keywords: ["DXGKCB_UNMAP_MEMORY callback function"]
ms.keywords: DXGKCB_UNMAP_MEMORY, DXGKCB_UNMAP_MEMORY callback, DpFunctions_d0ba5b02-22ab-4fad-a54a-1e402f538456.xml, DxgkCbUnmapMemory, DxgkCbUnmapMemory callback function [Display Devices], display.dxgkcbunmapmemory, dispmprt/DxgkCbUnmapMemory
f1_keywords:
 - "dispmprt/DxgkCbUnmapMemory"
 - "DxgkCbUnmapMemory"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dispmprt.h
api_name:
- DxgkCbUnmapMemory
targetos: Windows
req.typenames: 
---

# DXGKCB_UNMAP_MEMORY callback function


## -description


The <b>DxgkCbUnmapMemory</b> function unmaps a range of addresses previously mapped by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_map_memory">DxgkCbMapMemory</a>.


## -parameters




### -param DeviceHandle 
[in]
A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure that was passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>.


### -param VirtualAddress 
[in]
The beginning address of the range to be unmapped. This address can be a virtual address in system space, a virtual address in the address space of a user-mode process, or an address in I/O space.


## -returns



<b>DxgkCbUnmapMemory</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_map_memory">DxgkCbMapMemory</a>
 

 

