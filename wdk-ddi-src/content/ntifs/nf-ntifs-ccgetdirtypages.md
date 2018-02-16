---
UID: NF:ntifs.CcGetDirtyPages
title: CcGetDirtyPages function
author: windows-driver-content
description: The CcGetDirtyPages routine searches for dirty pages in all files that match a given log handle.
old-location: ifsk\ccgetdirtypages.htm
old-project: ifsk
ms.assetid: 8ca0d683-318b-465c-95a7-dc2b5e29c9e7
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ifsk.ccgetdirtypages, CcGetDirtyPages, ccref_cbefaf71-3c21-445f-ac63-d96bbb47ec16.xml, CcGetDirtyPages routine [Installable File System Drivers], ntifs/CcGetDirtyPages
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CcGetDirtyPages
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcGetDirtyPages function


## -description


The <b>CcGetDirtyPages</b> routine searches for dirty pages in all files that match a given log handle. 


## -syntax


````
LARGE_INTEGER CcGetDirtyPages(
  _In_ PVOID               LogHandle,
  _In_ PDIRTY_PAGE_ROUTINE DirtyPageRoutine,
  _In_ PVOID               Context1,
  _In_ PVOID               Context2
);
````


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

To set a log handle for a file, use <a href="..\ntifs\nf-ntifs-ccsetloghandleforfile.md">CcSetLogHandleForFile</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-ccsetloghandleforfile.md">CcSetLogHandleForFile</a>



<a href="..\ntifs\nf-ntifs-ccsetdirtypinneddata.md">CcSetDirtyPinnedData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcGetDirtyPages routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

