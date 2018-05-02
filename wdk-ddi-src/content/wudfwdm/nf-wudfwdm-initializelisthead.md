---
UID: NF:wudfwdm.InitializeListHead
title: InitializeListHead function
author: windows-driver-content
description: The InitializeListHead routine initializes a LIST_ENTRY structure that represents the head of a doubly linked list.
old-location: kernel\initializelisthead.htm
old-project: kernel
ms.assetid: 123434fd-4e83-4042-834b-1eb4cf13dd10
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: InitializeListHead, InitializeListHead routine [Kernel-Mode Driver Architecture], k109_2e5e02a0-26d3-4c8a-b712-ee3d515b8a23.xml, kernel.initializelisthead, wdm/InitializeListHead
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfwdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	InitializeListHead
product:
- Windows
targetos: Windows
req.typenames: 
---

# InitializeListHead function


## -description


The <b>InitializeListHead</b> routine initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure that represents the head of a doubly linked list.


## -parameters




### -param ListHead [out]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure that serves as the list header. 


## -returns



None




## -remarks



The <b>InitializeListHead</b> routine sets the <b>Flink</b> and <b>Blink</b> members of <i>ListHead</i> to point to <i>ListHead</i>.

For information about using this routine when implementing a doubly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

Callers of <b>InitializeListHead</b> can be running at any IRQL. If <b>InitializeListHead</b> is called at IRQL &gt;= DISPATCH_LEVEL the storage for <i>ListHead</i> must be resident.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545397">ExInterlockedInsertHeadList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545402">ExInterlockedInsertTailList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545408">ExInterlockedPopEntryList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545418">ExInterlockedPushEntryList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545427">ExInterlockedRemoveHeadList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547820">InsertHeadList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547823">InsertTailList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551789">IsListEmpty</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552160">KeInitializeSpinLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559712">PopEntryList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559964">PushEntryList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561029">RemoveEntryList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561032">RemoveHeadList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561036">RemoveTailList</a>
 

 



