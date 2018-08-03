---
UID: NF:wdm.ExInterlockedPushEntryList
title: ExInterlockedPushEntryList function
author: windows-driver-content
description: The ExInterlockedPushEntryList routine atomically inserts an entry at the beginning of a singly linked list of SINGLE_LIST_ENTRY structures.
old-location: kernel\exinterlockedpushentrylist.htm
tech.root: kernel
ms.assetid: 7a932f69-c5dd-4844-b461-b986c00a08c7
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: ExInterlockedPushEntryList, ExInterlockedPushEntryList routine [Kernel-Mode Driver Architecture], k102_dbf9c23d-8c9a-47e6-a923-cdb4d247148c.xml, kernel.exinterlockedpushentrylist, wdm/ExInterlockedPushEntryList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IoAllocateFree, IoReuseIrp, MarkingInterlockedQueuedIrps, RemoveLockCheck, RemoveLockForward, RemoveLockForward2, RemoveLockForwardDeviceControl, RemoveLockForwardDeviceControl2, RemoveLockForwardDeviceControlInternal, RemoveLockForwardDeviceControlInternal2, RemoveLockForwardRead, RemoveLockForwardRead2, RemoveLockForwardWrite, RemoveLockForwardWrite2, RemoveLockRelease2, RemoveLockReleaseCleanup, RemoveLockReleaseClose, RemoveLockReleaseCreate, RemoveLockReleaseDeviceControl, RemoveLockReleaseInternalDeviceControl, RemoveLockReleasePower, RemoveLockReleaseRead, RemoveLockReleaseShutdown, RemoveLockReleaseSystemControl, RemoveLockReleaseWrite
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExInterlockedPushEntryList
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExInterlockedPushEntryList function


## -description


The <b>ExInterlockedPushEntryList</b> routine atomically inserts an entry at the beginning of a singly linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563799">SINGLE_LIST_ENTRY</a> structures.


## -parameters




### -param ListHead [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563799">SINGLE_LIST_ENTRY</a> structure that serves as the list header.


### -param ListEntry [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563799">SINGLE_LIST_ENTRY</a> structure that represents the entry to be inserted into the list. 


### -param Lock [in, out]

A pointer to a <b>KSPIN_LOCK</b> structure that serves as the spin lock used to synchronize access to the list. The storage for the spin lock must be resident and must have been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff552160">KeInitializeSpinLock</a>. You must use this spin lock only with the <b>ExInterlocked<i>Xxx</i>List</b> routines.


## -returns



<b>ExInterlockedPushEntryList</b> returns a pointer to the first entry of the list <u>before</u> the new entry was inserted. If the list was empty, the routine returns <b>NULL</b>.




## -remarks



<b>ExInterlockedPushEntryList</b> performs the same operation as <a href="https://msdn.microsoft.com/library/windows/hardware/ff559964">PushEntryList</a>, but atomically. Do not mix atomic and non-atomic calls on the same list.

For more information about using this routine to implement a singly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

The <b>ExInterlockedPushEntryList</b> routine can be called at any IRQL. The storage for the <i>ListHead</i> parameter and the list entries must be resident at all IRQLs.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545321">ExInitializeSListHead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545402">ExInterlockedInsertTailList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545408">ExInterlockedPopEntryList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545422">ExInterlockedPushEntrySList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552160">KeInitializeSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559964">PushEntryList</a>
 

 

