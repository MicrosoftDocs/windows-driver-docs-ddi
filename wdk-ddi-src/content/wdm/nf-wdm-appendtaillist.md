---
UID: NF:wdm.AppendTailList
title: AppendTailList function
author: windows-driver-content
description: The AppendTailList routine appends a doubly linked list of LIST_ENTRY structures to the tail of another doubly linked list of LIST_ENTRY structures.
old-location: kernel\appendtaillist.htm
old-project: kernel
ms.assetid: A7C7FBE5-9046-48C7-AEE6-85C17CDE83AD
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: AppendTailList, AppendTailList routine [Kernel-Mode Driver Architecture], kernel.appendtaillist, wdm/AppendTailList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: Any level (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	AppendTailList
product: Windows
targetos: Windows
req.typenames: 
---

# AppendTailList function


## -description


The <b>AppendTailList</b> routine appends a doubly linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structures to the tail of another doubly linked list of <b>LIST_ENTRY</b> structures.


## -parameters




### -param ListHead [in, out]

A pointer to the head of the list to which the list pointed to by <i>ListToAppend</i> is to be appended. This parameter must be a valid, non-NULL pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure that is the head of a list. This list can be empty.


### -param ListToAppend [in, out]

A pointer to the first entry in the list to append to the list pointed to by <i>ListHead</i>. This parameter must be a valid, non-NULL pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure that is the first entry in a headless list. For more information, see Remarks.


## -returns



None.




## -remarks



This routine constructs a list that contains all the combined entries from the input <i>ListHead</i> and <i>ListToAppend</i> lists. When the routine returns, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure pointed to by the <i>ListHead</i> parameter is the head of the resulting combined list. The <b>LIST_ENTRY</b> structure pointed to by the <i>ListToAppend</i> parameter is an entry in the resulting combined list.

The caller sets the <i>ListToAppend</i> parameter to point to the first entry in the list to be appended. In this regard, <i>AppendTailList</i> does not conform to the convention followed by the other doubly linked list routines that use the <b>LIST_ENTRY</b> structure. In these other routines, a parameter that represents a list points to the list head instead of to the first entry in the list. If your driver code uses a list head to represent the list to be appended, the list head must be removed from this list before the list is passed as the <i>ListToAppend</i> parameter to <b>AppendTailList</b>. For a code example that shows how to remove this list head, see Examples.

<b>AppendTailList</b> can be used to insert a single entry at the tail of a list, but the <b>Flink</b> and <b>Blink</b> members of the <b>LIST_ENTRY</b> structure pointed to by <i>ListToAppend</i> must first be initialized—typically, by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547799">InitializeListHead</a> routine. In contrast, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547823">InsertTailList</a> routine does not require the <b>Flink</b> and <b>Blink</b> members of the <b>LIST_ENTRY</b> structure pointed to by the <i>Entry</i> parameter to be initialized before the <b>InsertTailList</b> call. For this reason, <b>InsertTailList</b> might be more convenient to use to insert a single entry at the tail of a list.

A driver can access the <b>Flink</b> and <b>Blink</b> members of a <b>LIST_ENTRY</b>, but the members must only be updated by the system routines supplied for this purpose.

For information about using this routine when implementing a doubly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

Callers of <b>AppendTailList</b> can be running at any IRQL. If <b>AppendTailList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for the list entries must be memory-resident.


#### Examples

The following code example shows how to write a function named <code>MyAppendTailList</code> that is similar to <b>AppendTailList</b>, but that treats the <i>ListToAppend</i> parameter as a pointer to a list head instead of as a pointer to the first entry in a (headless) list. Unlike <b>AppendTailList</b>, the <code>MyAppendTailList</code> function avoids including the <b>LIST_ENTRY</b> structure pointed to by the <i>ListToAppend</i> parameter in the entries that are appended to the list pointed to by the <i>ListHead</i> parameter.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID MyAppendTailList(
    _Inout_  PLIST_ENTRY ListHead,
    _Inout_  PLIST_ENTRY ListToAppend
    )
{
    PLIST_ENTRY entry = ListToAppend-&gt;Flink;

    if (!IsListEmpty(ListToAppend))
    {
        RemoveEntryList(ListToAppend);
        InitializeListHead(ListToAppend);
        AppendTailList(ListHead, entry);
    }
}
</pre>
</td>
</tr>
</table></span></div>
The <code>MyAppendTailList</code> function in this code example treats both the <i>ListHead</i> and <i>ListToAppend</i> parameters as pointers to list heads. When this function returns, the list pointed to by <i>ListToAppend</i> is empty; that is, it consists of a list head that has no associated list entries. All of the entries that were initially in this list have been appended to the list pointed to by <i>ListHead</i>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547799">InitializeListHead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547823">InsertTailList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561029">RemoveEntryList</a>
 

 

