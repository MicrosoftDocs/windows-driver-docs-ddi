---
UID: NA:spb
ms.assetid: e794df0d-60f5-3c88-a345-ed17d683adf2
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Spb.h header



This header is used by SPB. For more information, see
- [SPB](../_SPB/index.md)

Spb.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST function](nf-spb-spb_transfer_list_entry_init_buffer_list.md) | The SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST function returns an SPB_TRANSFER_LIST_ENTRY structure that is initialized to describe a scatter-gather list.SPB_TRANSFER_LIST_ENTRY_INIT_BUFFER_LIST function returns an SPB_TRANSFER_LIST_ENTRY structure that is initialized to describe a scatter-gather list. |
| [SPB_TRANSFER_LIST_ENTRY_INIT_MDL function](nf-spb-spb_transfer_list_entry_init_mdl.md) | The SPB_TRANSFER_LIST_ENTRY_INIT_MDL function returns an SPB_TRANSFER_LIST_ENTRY structure that is initialized to use an MDL to describe a data buffer. |
| [SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED function](nf-spb-spb_transfer_list_entry_init_non_paged.md) | The SPB_TRANSFER_LIST_ENTRY_INIT_NON_PAGED function returns an SPB_TRANSFER_LIST_ENTRY structure that is initialized to describe a simple data buffer in nonpaged memory. |
| [SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE function](nf-spb-spb_transfer_list_entry_init_simple.md) | The SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE function returns an SPB_TRANSFER_LIST_ENTRY structure that is initialized to describe a simple data buffer.SPB_TRANSFER_LIST_ENTRY_INIT_SIMPLE function returns an SPB_TRANSFER_LIST_ENTRY structure that is initialized to describe a simple data buffer. |
| [SPB_TRANSFER_LIST_INIT function](nf-spb-spb_transfer_list_init.md) | The SPB_TRANSFER_LIST_INIT function initializes an SPB_TRANSFER_LIST structure. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [SPB_TRANSFER_BUFFER structure](ns-spb-spb_transfer_buffer.md) | The SPB_TRANSFER_BUFFER structure describes the data buffer for an individual transfer in an I/O transfer sequence. |
| [SPB_TRANSFER_BUFFER_LIST_ENTRY structure](ns-spb-spb_transfer_buffer_list_entry.md) | The SPB_TRANSFER_BUFFER_LIST_ENTRY structure describes either a simple transfer buffer, or an element in an array of one or more transfer buffers. |
| [SPB_TRANSFER_LIST structure](ns-spb-spb_transfer_list.md) | The SPB_TRANSFER_LIST structure describes an I/O transfer sequence. |
| [SPB_TRANSFER_LIST_ENTRY structure](ns-spb-spb_transfer_list_entry.md) | The SPB_TRANSFER_LIST_ENTRY structure describes a single transfer in an I/O transfer sequence. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [SPB_TRANSFER_BUFFER_FORMAT enumeration](ne-spb-spb_transfer_buffer_format.md) | The SPB_TRANSFER_BUFFER_FORMAT enumeration specifies the format of the buffer that is described by an SPB_TRANSFER_BUFFER structure. |
| [SPB_TRANSFER_DIRECTION enumeration](ne-spb-spb_transfer_direction.md) | The SPB_TRANSFER_DIRECTION enumeration describes the direction (read or write) of a single transfer in an I/O transfer sequence. |
| [SpbIoctl enumeration](ne-spb-spbioctl.md) | Defines values to indicate the type I/O control request. |
