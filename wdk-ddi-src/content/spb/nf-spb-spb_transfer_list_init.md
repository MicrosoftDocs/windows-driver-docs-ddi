---
UID: NF:spb.SPB_TRANSFER_LIST_INIT
title: SPB_TRANSFER_LIST_INIT function (spb.h)
description: The SPB_TRANSFER_LIST_INIT function initializes an SPB_TRANSFER_LIST structure.
old-location: spb\spb_transfer_list_init.htm
tech.root: SPB
ms.date: 11/15/2021
keywords: ["SPB_TRANSFER_LIST_INIT function"]
ms.keywords: SPB.spb_transfer_list_init, SPB_TRANSFER_LIST_INIT, SPB_TRANSFER_LIST_INIT function [Buses], spb/SPB_TRANSFER_LIST_INIT
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - SPB_TRANSFER_LIST_INIT
 - spb/SPB_TRANSFER_LIST_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Spb.h
api_name:
 - SPB_TRANSFER_LIST_INIT
---

# SPB_TRANSFER_LIST_INIT function

## -description

The **SPB_TRANSFER_LIST_INIT** function initializes an [SPB_TRANSFER_LIST](./ns-spb-spb_transfer_list.md) structure.

## -parameters

### -param TransferList [out]

A pointer to the **SPB_TRANSFER_LIST** structure that is to be initialized.

### -param TransferCount [in]

The number of entries in the transfer list. The function writes this value to the **TransferCount** member of the **SPB_TRANSFER_LIST** structure.

## -remarks

To initialize the elements in the **SPB_TRANSFER_LIST** structure's **Transfers** array, use the [SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE](./nf-spb-spb_transfer_list_entry_init_simple.md), [SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED](./nf-spb-spb_transfer_list_entry_init_non_paged.md), or [SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST](./nf-spb-spb_transfer_list_entry_init_buffer_list.md) function.

## -see-also

- [SPB_TRANSFER_LIST](./ns-spb-spb_transfer_list.md)
- [SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST](./nf-spb-spb_transfer_list_entry_init_buffer_list.md)
- [SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED](./nf-spb-spb_transfer_list_entry_init_non_paged.md)
- [SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE](./nf-spb-spb_transfer_list_entry_init_simple.md)
