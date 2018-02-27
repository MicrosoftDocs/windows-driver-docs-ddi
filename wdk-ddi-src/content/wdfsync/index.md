---
UID: NA:wdfsync
ms.assetid: 48b6478c-096f-337a-8dda-9d38136431bc
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdfsync.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdfsync.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WdfSpinLockCreate function](nf-wdfsync-wdfspinlockcreate.md) | The WdfSpinLockCreate method creates a framework spin-lock object. |
| [WdfWaitLockAcquire function](nf-wdfsync-wdfwaitlockacquire.md) | The WdfWaitLockAcquire method acquires a specified wait lock. |
| [WdfWaitLockCreate function](nf-wdfsync-wdfwaitlockcreate.md) | The WdfWaitLockCreate method creates a framework wait-lock object. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PFN_WDFOBJECTACQUIRELOCK callback](nc-wdfsync-pfn_wdfobjectacquirelock.md) | The WdfObjectAcquireLock method acquires an object's synchronization lock. |
| [PFN_WDFOBJECTRELEASELOCK callback](nc-wdfsync-pfn_wdfobjectreleaselock.md) | The WdfObjectReleaseLock method releases an object's synchronization lock. |
