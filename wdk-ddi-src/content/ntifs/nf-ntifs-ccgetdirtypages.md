---
UID: NF:ntifs.CcGetDirtyPages
title: CcGetDirtyPages function (ntifs.h)
description: The CcGetDirtyPages routine searches for dirty pages in all files that match a given log handle.
old-location: ifsk\ccgetdirtypages.htm
tech.root: ifsk
ms.assetid: 8ca0d683-318b-465c-95a7-dc2b5e29c9e7
ms.date: 04/16/2018
keywords: ["CcGetDirtyPages function"]
ms.keywords: CcGetDirtyPages, CcGetDirtyPages routine [Installable File System Drivers], ccref_cbefaf71-3c21-445f-ac63-d96bbb47ec16.xml, ifsk.ccgetdirtypages, ntifs/CcGetDirtyPages
f1_keywords:
 - "ntifs/CcGetDirtyPages"
 - "CcGetDirtyPages"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available on Microsoft Windows XP and later.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- CcGetDirtyPages
product:
- Windows
targetos: Windows
req.typenames: 
---

# CcGetDirtyPages function


## -description


The <b>CcGetDirtyPages</b> routine searches for dirty pages in all files that match a given log handle. 


## -parameters




### -param LogHandle [in]

Log handle stored by a previous call to <b>CcSetLogHandleForFile</b>. 


### -param DirtyPageRoutine [in]

Pointer to a callback routine that builds up a dirty page table from the pages found. This routine, which is called for each dirty page found, is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID (*PDIRTY_PAGE_ROUTINE) (
            IN PFILE_OBJECT FileObject,
            IN PLARGE_INTEGER FileOffset,
            IN ULONG Length,
            IN PLARGE_INTEGER OldestLsn,
            IN PLARGE_INTEGER NewestLsn,
            IN PVOID Context1,
            IN PVOID Context2
            );</pre>
</td>
</tr>
</table></span></div>




#### FileObject

Pointer to the file object for the file containing the dirty page. 



#### FileOffset

Pointer to a variable that specifies the starting byte offset of the dirty page within the cached file. 



#### Length

Length, in bytes, of the dirty page. 



#### OldestLsn

Oldest logical sequence number (LSN) found in the dirty page. 



#### NewestLsn

Newest LSN found in the dirty page. 



#### Context1

First context parameter. 



#### Context2

Second context parameter. 


### -param Context1 [in]

First context parameter to be passed to the <i>DirtyPageRoutine</i>. 


### -param Context2 [in]

Second context parameter to be passed to the <i>DirtyPageRoutine</i>. 


## -returns



<b>CcGetDirtyPages</b> returns the oldest LSN found in the set of dirty pages. If there are no dirty pages, <b>CcGetDirtyPages</b> returns zero. 




## -remarks



File systems call <b>CcGetDirtyPages</b> to return dirty pages in all files that match a given log handle. <b>CcGetDirtyPages</b> searches for dirty pages in all files that match the given <i>LogHandle</i> and calls the <i>DirtyPageRoutine</i> for each page. 

To set a log handle for a file, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539217">CcSetLogHandleForFile</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539211">CcSetDirtyPinnedData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539217">CcSetLogHandleForFile</a>
 

 

