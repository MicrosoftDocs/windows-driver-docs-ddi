---
UID: NC:dispmprt.DXGKCB_MAP_MEMORY
title: DXGKCB_MAP_MEMORY (dispmprt.h)
description: The DxgkCbMapMemory function maps a range of translated physical addresses (associated with a memory resource assigned to a display adapter) into system space or the virtual address space of a user-mode process.
old-location: display\dxgkcbmapmemory.htm
tech.root: display
ms.date: 04/01/2021
keywords: ["DXGKCB_MAP_MEMORY callback function"]
ms.keywords: DXGKCB_MAP_MEMORY, DXGKCB_MAP_MEMORY callback, DpFunctions_51d99a74-2fae-40b7-9e04-8afe0fc38805.xml, DxgkCbMapMemory, DxgkCbMapMemory callback function [Display Devices], display.dxgkcbmapmemory, dispmprt/DxgkCbMapMemory
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
targetos: Windows
req.typenames: 
f1_keywords:
 - DXGKCB_MAP_MEMORY
 - dispmprt/DXGKCB_MAP_MEMORY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKCB_MAP_MEMORY
---

# DXGKCB_MAP_MEMORY callback function

## -description

The **DxgkCbMapMemory** function maps a range of translated physical addresses (associated with a memory resource assigned to a display adapter) into system space or the virtual address space of a user-mode process.

## -parameters

### -param DeviceHandle

[in] A handle that represents a display adapter. The display miniport driver previously obtained this handle in the **DeviceHandle** member of the [**DXGKRNL_INTERFACE**](ns-dispmprt-_dxgkrnl_interface.md) structure that was passed to [**DxgkDdiStartDevice**](nc-dispmprt-dxgkddi_start_device.md).

### -param TranslatedAddress

[in] The base translated physical address of the memory range to be mapped. The display miniport driver previously obtained this address by calling [**DxgkCbGetDeviceInformation**](nc-dispmprt-dxgkcb_get_device_information.md).

### -param Length

[in] The size, in bytes, of the range to be mapped.

### -param InIoSpace

[in] A Boolean value that specifies whether the range is in I/O space (**TRUE**) or memory space (**FALSE**).

### -param MapToUserMode

[in] A Boolean value that specifies whether the range is mapped into user-mode space or system space. If **TRUE**, the range is mapped into the (user-mode) virtual address space of the current process. If **FALSE**, the range is mapped into system space. If **InIoSpace** is **TRUE**, this parameter is ignored.

### -param CacheType

[in] A [**MEMORY_CACHING_TYPE**](../wdm/ne-wdm-_memory_caching_type.md) enumerator that specifies the caching behavior of the mapped range.

### -param VirtualAddress

[out] A pointer to a variable that receives the address of the beginning of the mapped range. The way that the mapped range is accessed depends on the values of **InIoSpace** and **MapToUserMode**. The following table summarizes the different ways that the mapped range is accessed.

| Value of InIoSpace | MapToUserMode is FALSE           | MapToUserMode is TRUE |
| ------------------ |-----------------------           | --------------------- |
| FALSE              | READ_REGISTER_X WRITE_REGISTER_X | User-mode code performs ordinary memory access.|
| TRUE               | READ_PORT_X WRITE_PORT_X         | Not possible. |

## -returns

**DxgkCbMapMemory** returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in **Ntstatus.h**.

## -remarks

The PHYSICAL_ADDRESS data type is defined in **Ntdef.h**.

## -see-also

[**MEMORY_CACHING_TYPE**](../wdm/ne-wdm-_memory_caching_type.md)
