---
UID: NS:wdbgexts._POINTER_SEARCH_PHYSICAL
title: "_POINTER_SEARCH_PHYSICAL"
author: windows-driver-content
description: The IG_POINTER_SEARCH_PHYSICAL Ioctl operation searches the target's physical memory for pointers lying within a specified range.
old-location: debugger\ig_pointer_search_physical.htm
old-project: debugger
ms.assetid: fdb8376b-fbda-4bee-895e-a306fd0f632a
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: POINTER_SEARCH_PHYSICAL, PPOINTER_SEARCH_PHYSICAL, WdbgExts_Ref_ce742570-c023-4e34-a8e2-aef530e61c04.xml, PPOINTER_SEARCH_PHYSICAL structure pointer [Windows Debugging], _POINTER_SEARCH_PHYSICAL, wdbgexts/PPOINTER_SEARCH_PHYSICAL, POINTER_SEARCH_PHYSICAL structure [Windows Debugging], *PPOINTER_SEARCH_PHYSICAL, debugger.ig_pointer_search_physical, wdbgexts/POINTER_SEARCH_PHYSICAL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdbgexts.h
apiname:
-	POINTER_SEARCH_PHYSICAL
product: Windows
targetos: Windows
req.typenames: POINTER_SEARCH_PHYSICAL, *PPOINTER_SEARCH_PHYSICAL
req.product: Windows 10 or later.
---

# _POINTER_SEARCH_PHYSICAL structure


## -description


The IG_POINTER_SEARCH_PHYSICAL <a href="..\wdbgexts\nc-wdbgexts-pwindbg_ioctl_routine.md">Ioctl</a> operation searches the target's physical memory for pointers lying within a specified range.  When calling <b>Ioctl</b> with <i>IoctlType</i> set to IG_POINTER_SEARCH_PHYSICAL, <i>IpvData</i> should contain an instance of the POINTER_SEARCH_PHYSICAL structure.


## -syntax


````
typedef struct _POINTER_SEARCH_PHYSICAL {
  ULONG64  Offset;
  ULONG64  Length;
  ULONG64  PointerMin;
  ULONG64  PointerMax;
  ULONG    Flags;
  PULONG64 MatchOffsets;
  ULONG    MatchOffsetsSize;
  ULONG    MatchOffsetsCount;
} POINTER_SEARCH_PHYSICAL, *PPOINTER_SEARCH_PHYSICAL;
````


## -struct-fields




### -field Offset

Specifies the address in the target's physical memory to start searching from.


### -field Length

Specifies the amount of the target's physical memory to search.


### -field PointerMin

Specifies the lower limit of the range of pointers to search for.


### -field PointerMax

Specifies the upper limit of the range of pointers to search for.


### -field Flags

Specifies bit flags that alter the behavior of this <b>Ioctl</b> operation.  The following flags can be included.
<table>
<tr>
<th>Flag</th>
<th>Behavior when set</th>
</tr>
<tr>
<td>
PTR_SEARCH_PHYS_ALL_HITS

</td>
<td>
Return all pointers in the specified range.  If this flag is not set, only one pointer per page is returned.

</td>
</tr>
<tr>
<td>
PTR_SEARCH_PHYS_PTE

</td>
<td>
The memory is searched for a page table entry (PTE) that matches the Page Frame Number specified in <b>PointerMin</b>.

</td>
</tr>
<tr>
<td>
PTR_SEARCH_PHYS_RANGE_CHECK_ONLY

</td>
<td>


</td>
</tr>
<tr>
<td>
PTR_SEARCH_NO_SYMBOL_CHECK

</td>
<td>
Do not check that the symbols used for the kernel are correct.

</td>
</tr>
</table> 


### -field MatchOffsets

Receives the addresses of all the pointers that match the search criteria.  <b>MatchOffsets</b> is an array that contains <b>MatchOffsetsSize</b> elements.


### -field MatchOffsetsSize

Specifies the number of entries in the array <b>MatchOffsets</b>.


### -field MatchOffsetsCount

Receives the number of pointers found that match the search criteria.


## -remarks


The parameters for the IG_POINTER_SEARCH_PHYSICAL <a href="..\wdbgexts\nc-wdbgexts-pwindbg_ioctl_routine.md">Ioctl</a> operation are the members of the POINTER_SEARCH_PHYSICAL structure.



## -see-also

<a href="..\wdbgexts\nc-wdbgexts-pwindbg_ioctl_routine.md">Ioctl</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20POINTER_SEARCH_PHYSICAL structure%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

