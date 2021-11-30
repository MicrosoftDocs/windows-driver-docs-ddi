---
UID: NF:spb.SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED
title: SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED function (spb.h)
description: The SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED function returns an SPB_TRANSFER_LIST_ENTRY structure that is initialized to describe a simple data buffer in nonpaged memory.
old-location: spb\spb_transfer_list_entry_init_non_paged.htm
tech.root: SPB
ms.date: 11/15/2021
keywords: ["SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED function"]
ms.keywords: SPB.spb_transfer_list_entry_init_non_paged, SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED, SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED function [Buses], spb/SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED
req.header: spb.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: Any IRQL
targetos: Windows
req.typenames: 
f1_keywords:
 - SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED
 - spb/SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Spb.h
api_name:
 - SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED
---

# SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED function

## -description

The **SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED** function returns an [SPB_TRANSFER_LIST_ENTRY](./ns-spb-spb_transfer_list_entry.md) structure that is initialized to describe a simple data buffer in non-paged memory.

## -parameters

### -param Direction [in]

The direction of the transfer. The function writes this value to the **Direction** member of the **SPB_TRANSFER_LIST_ENTRY** structure.

### -param DelayInUs [in]

An optional delay in microseconds. The function writes this value to the **DelayInUs** member of the **SPB_TRANSFER_LIST_ENTRY** structure.

### -param Buffer [in]

A pointer to a data buffer. The function writes this value to the **Buffer.Simple.Buffer** member of the **SPB_TRANSFER_LIST_ENTRY** structure. For more information, see the description of the **Buffer** member in [SPB_TRANSFER_BUFFER_LIST_ENTRY](./ns-spb-spb_transfer_buffer_list_entry.md).

### -param BufferCb [in]

The size, in bytes, of the buffer pointed to by _Buffer_. The function writes this value to the **Buffer.Simple.BufferCb** member of the **SPB_TRANSFER_LIST_ENTRY** structure. For more information, see the description of the **BufferCb** member in [SPB_TRANSFER_BUFFER_LIST_ENTRY](./ns-spb-spb_transfer_buffer_list_entry.md).

## -returns

**SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED** returns an initialized **SPB_TRANSFER_LIST_ENTRY** structure.

## -remarks

This initialization function returns an unnamed local variable of type **SPB_TRANSFER_LIST_ENTRY**. The storage for this variable is allocated in the caller's stack frame and is valid while the stack frame remains in scope.

**SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED** sets the **Buffer.Format** member of the **SPB_TRANSFER_LIST_ENTRY** structure to **SpbTransferBufferFormatSimpleNonPaged**. For more information about buffer formats, see [SPB_TRANSFER_BUFFER_FORMAT](./ne-spb-spb_transfer_buffer_format.md).

## -see-also

- [SPB_TRANSFER_BUFFER_FORMAT](./ne-spb-spb_transfer_buffer_format.md)
- [SPB_TRANSFER_BUFFER_LIST_ENTRY](./ns-spb-spb_transfer_buffer_list_entry.md)
- [SPB_TRANSFER_LIST_ENTRY](./ns-spb-spb_transfer_list_entry.md)
