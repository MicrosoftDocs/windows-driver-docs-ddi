---
UID: NS:wdbgexts._POINTER_SEARCH_PHYSICAL
title: _POINTER_SEARCH_PHYSICAL (wdbgexts.h)
description: The IG_POINTER_SEARCH_PHYSICAL Ioctl operation searches the target's physical memory for pointers lying within a specified range.
old-location: debugger\ig_pointer_search_physical.htm
tech.root: debugger
ms.assetid: fdb8376b-fbda-4bee-895e-a306fd0f632a
ms.date: 05/03/2018
keywords: ["POINTER_SEARCH_PHYSICAL structure"]
ms.keywords: "*PPOINTER_SEARCH_PHYSICAL, POINTER_SEARCH_PHYSICAL, POINTER_SEARCH_PHYSICAL structure [Windows Debugging], PPOINTER_SEARCH_PHYSICAL, PPOINTER_SEARCH_PHYSICAL structure pointer [Windows Debugging], WdbgExts_Ref_ce742570-c023-4e34-a8e2-aef530e61c04.xml, _POINTER_SEARCH_PHYSICAL, debugger.ig_pointer_search_physical, wdbgexts/POINTER_SEARCH_PHYSICAL, wdbgexts/PPOINTER_SEARCH_PHYSICAL"
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
targetos: Windows
req.typenames: POINTER_SEARCH_PHYSICAL, *PPOINTER_SEARCH_PHYSICAL
f1_keywords:
 - _POINTER_SEARCH_PHYSICAL
 - wdbgexts/_POINTER_SEARCH_PHYSICAL
 - PPOINTER_SEARCH_PHYSICAL
 - wdbgexts/PPOINTER_SEARCH_PHYSICAL
 - POINTER_SEARCH_PHYSICAL
 - wdbgexts/POINTER_SEARCH_PHYSICAL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdbgexts.h
api_name:
 - POINTER_SEARCH_PHYSICAL
---

# _POINTER_SEARCH_PHYSICAL structure


## -description

The IG_POINTER_SEARCH_PHYSICAL <a href="/windows-hardware/drivers/ddi/wdbgexts/nc-wdbgexts-pwindbg_ioctl_routine">Ioctl</a> operation searches the target's physical memory for pointers lying within a specified range.  When calling <b>Ioctl</b> with <i>IoctlType</i> set to IG_POINTER_SEARCH_PHYSICAL, <i>IpvData</i> should contain an instance of the POINTER_SEARCH_PHYSICAL structure.

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

The parameters for the IG_POINTER_SEARCH_PHYSICAL <a href="/windows-hardware/drivers/ddi/wdbgexts/nc-wdbgexts-pwindbg_ioctl_routine">Ioctl</a> operation are the members of the POINTER_SEARCH_PHYSICAL structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdbgexts/nc-wdbgexts-pwindbg_ioctl_routine">Ioctl</a>