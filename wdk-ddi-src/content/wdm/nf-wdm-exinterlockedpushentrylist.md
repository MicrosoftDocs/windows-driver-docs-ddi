---
UID: NF:wdm.ExInterlockedPushEntryList
title: ExInterlockedPushEntryList function
author: windows-driver-content
description: The ExInterlockedPushEntryList routine atomically inserts an entry at the beginning of a singly linked list of SINGLE_LIST_ENTRY structures.
old-location: kernel\exinterlockedpushentrylist.htm
old-project: kernel
ms.assetid: 7a932f69-c5dd-4844-b461-b986c00a08c7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExInterlockedPushEntryList routine [Kernel-Mode Driver Architecture], ExInterlockedPushEntryList, kernel.exinterlockedpushentrylist, wdm/ExInterlockedPushEntryList, k102_dbf9c23d-8c9a-47e6-a923-cdb4d247148c.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExInterlockedPushEntryList
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExInterlockedPushEntryList function


## -description


The <b>ExInterlockedPushEntryList</b> routine atomically inserts an entry at the beginning of a singly linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563799">SINGLE_LIST_ENTRY</a> structures.


## -syntax


````
PSINGLE_LIST_ENTRY ExInterlockedPushEntryList(
  _Inout_ PSINGLE_LIST_ENTRY ListHead,
  _Inout_ PSINGLE_LIST_ENTRY ListEntry,
  _Inout_ PKSPIN_LOCK        Lock
);
````


## -parameters




### -param ListHead [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563799">SINGLE_LIST_ENTRY</a> structure that serves as the list header.


### -param ListEntry [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563799">SINGLE_LIST_ENTRY</a> structure that represents the entry to be inserted into the list. 


### -param Lock [in, out]

A pointer to a <b>KSPIN_LOCK</b> structure that serves as the spin lock used to synchronize access to the list. The storage for the spin lock must be resident and must have been initialized by calling <a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>. You must use this spin lock only with the <b>ExInterlocked<i>Xxx</i>List</b> routines.


## -returns



<b>ExInterlockedPushEntryList</b> returns a pointer to the first entry of the list <u>before</u> the new entry was inserted. If the list was empty, the routine returns <b>NULL</b>.




## -remarks



<b>ExInterlockedPushEntryList</b> performs the same operation as <a href="..\wdm\nf-wdm-pushentrylist.md">PushEntryList</a>, but atomically. Do not mix atomic and non-atomic calls on the same list.

For more information about using this routine to implement a singly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

The <b>ExInterlockedPushEntryList</b> routine can be called at any IRQL. The storage for the <i>ListHead</i> parameter and the list entries must be resident at all IRQLs.




## -see-also

<a href="..\wdm\nf-wdm-keinitializespinlock.md">KeInitializeSpinLock</a>



<a href="..\wdm\nf-wdm-exinterlockedpushentryslist.md">ExInterlockedPushEntrySList</a>



<a href="..\wdm\nf-wdm-pushentrylist.md">PushEntryList</a>



<a href="..\wdm\nf-wdm-exinterlockedpopentrylist.md">ExInterlockedPopEntryList</a>



<a href="..\wdm\nf-wdm-initializeslisthead.md">ExInitializeSListHead</a>



<a href="..\wdm\nf-wdm-exinterlockedinserttaillist.md">ExInterlockedInsertTailList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExInterlockedPushEntryList routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

