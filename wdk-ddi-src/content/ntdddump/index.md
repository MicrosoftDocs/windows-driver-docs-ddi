---
UID: NA:ntdddump
ms.assetid: 10b70e56-f6c4-3716-b71b-c70b212a4fa0
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ntdddump.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Ntdddump.h contain these programming interfaces:


## Callback functions

| Title   | Description   |
| ---- |:---- |
| [DUMP_FINISH callback](nc-ntdddump-dump_finish.md) | The Dump_Finish callback routine is called after writing all the dump data. The dump port driver generally flushes the cache to ensure the data is stored on the storage media before the system powers down. |
| [DUMP_READ callback](nc-ntdddump-dump_read.md) | The Dump_Read callback routine is called after the read from the dump port driver. The filter driver can access the dump data during the call to this routine. |
| [DUMP_START callback](nc-ntdddump-dump_start.md) | The Dump_Start callback routine is called after initializing the dump driver and just before starting the dump write process. |
| [DUMP_UNLOAD callback](nc-ntdddump-dump_unload.md) | The Dump_Unload callback routine is called when the dump stack is unloaded. |
| [DUMP_WRITE callback](nc-ntdddump-dump_write.md) | The Dump_Write callback routine is called before the write to the dump port driver. The filter driver can access the dump data at this time. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_FILTER_EXTENSION structure](ns-ntdddump-_filter_extension.md) | The crash dump driver passes a pointer to a FILTER_EXTENSION structure when the filter driver callback routines are called. |
| [_FILTER_INITIALIZATION_DATA structure](ns-ntdddump-_filter_initialization_data.md) | The filter driver fills in a FILTER_INITIALIZATION_DATA structure and returns it to the crash dump driver. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_FILTER_DUMP_TYPE enumeration](ne-ntdddump-_filter_dump_type.md) | The FILTER_DUMP_TYPE enumeration indicates the type of dump stack that this instance of the filter driver is loaded on. |
