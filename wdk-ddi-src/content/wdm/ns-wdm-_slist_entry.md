---
UID: NS:wdm._SLIST_ENTRY
title: "_SLIST_ENTRY"
author: windows-driver-content
description: An SLIST_ENTRY structure describes an entry in a sequenced singly linked list.
old-location: kernel\slist_entry.htm
old-project: kernel
ms.assetid: 690bcd8a-3c4f-4254-99c7-4ad600b4ae4f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSLIST_ENTRY, PSLIST_ENTRY, PSLIST_ENTRY structure pointer [Kernel-Mode Driver Architecture], SLIST_ENTRY, SLIST_ENTRY structure [Kernel-Mode Driver Architecture], _SLIST_ENTRY, kernel.slist_entry, kstruct_d_2bfe90ad-ee2e-4dbf-a028-5b3481aa8695.xml, wdm/PSLIST_ENTRY, wdm/SLIST_ENTRY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	SLIST_ENTRY
product: Windows
targetos: Windows
req.typenames: SLIST_ENTRY, *PSLIST_ENTRY
req.product: Windows 10 or later.
---

# _SLIST_ENTRY structure


## -description


An <b>SLIST_ENTRY</b> structure describes an entry in a sequenced singly linked list.


## -syntax


````
typedef struct _SLIST_ENTRY {
  struct _SLIST_ENTRY  *Next;
} SLIST_ENTRY, *PSLIST_ENTRY;
````


## -struct-fields




### -field Next

Pointer to the next entry in the list, or <b>NULL</b> if there is no next entry in the list.


### -field _SLIST_ENTRY

 




## -remarks



A driver can access the <b>Next</b> member of a <b>SLIST_ENTRY</b>, but must only be updated by the system routines supplied for this purpose.

On 64-bit platforms, <b>SLIST_ENTRY</b> structures must be 16-byte aligned. Drivers can use DECLSPEC_ALIGN(MEMORY_ALLOCATION_ALIGNMENT) to ensure the proper alignment of <b>SLIST_ENTRY</b>.

For more information about how to use <b>SLIST_ENTRY</b> structures to implement a sequenced singly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.




## -see-also

<a href="..\wdm\nf-wdm-exinterlockedpushentryslist.md">ExInterlockedPushEntrySList</a>



<a href="..\wdm\nf-wdm-exinterlockedflushslist.md">ExInterlockedFlushSList</a>



<a href="..\wdm\nf-wdm-exinterlockedpopentryslist.md">ExInterlockedPopEntrySList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SLIST_ENTRY structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

