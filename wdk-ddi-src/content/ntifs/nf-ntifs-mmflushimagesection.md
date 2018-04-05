---
UID: NF:ntifs.MmFlushImageSection
title: MmFlushImageSection function
author: windows-driver-content
description: The MmFlushImageSection routine flushes the image section for a file.
old-location: ifsk\mmflushimagesection.htm
old-project: ifsk
ms.assetid: e5c94f80-8ff8-4945-b1b8-a12190c3dec7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: MmFlushImageSection, MmFlushImageSection routine [Installable File System Drivers], ifsk.mmflushimagesection, mmref_d6a37cf0-a204-4070-80f6-bd407f671ee8.xml, ntifs/MmFlushImageSection
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmFlushImageSection
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# MmFlushImageSection function


## -description


The <b>MmFlushImageSection</b> routine flushes the image section for a file.


## -parameters




### -param SectionObjectPointer

TBD


### -param FlushType [in]

Specifies the reason for the flush operation. It can be one of the values listed in the following table. 

<table>
<tr>
<th>FlushType Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>MmFlushForDelete</b>

</td>
<td>
The file is being deleted. 

</td>
</tr>
<tr>
<td>
<b>MmFlushForWrite</b>

</td>
<td>
The file is being opened for write access. 

</td>
</tr>
</table>
 


#### - SectionPointer [in]

Pointer to a structure that contains the file object's section object pointers.


## -returns



<b>MmFlushImageSection</b> returns <b>TRUE</b> if the flush operation is successful, or if no image section exists for the file; otherwise <b>MmFlushImageSection</b> returns <b>FALSE</b>.

<div class="alert"><b>Note</b>  If the FlushType MmFlushForDelete value is specified and there are one or more outstanding write probes on the file's data section, <b>MmFlushImageSection</b> returns <b>FALSE</b>.</div>
<div> </div>



## -remarks



A file system must call the <b>MmFlushImageSection</b> routine before deleting a file or opening a file for write access. 

Before deleting a file, the file system should call <b>MmFlushImageSection</b> from its IRP_MJ_SET_INFORMATION or IRP_MJ_CLEANUP dispatch routine, passing <b>MmFlushForDelete</b> for the <i>FlushType</i> parameter. 

When opening a file for write access, the file system should call <b>MmFlushImageSection</b> from its IRP_MJ_CREATE dispatch routine, passing <b>MmFlushForWrite</b> for the <i>FlushType</i> parameter. 

If there are no mapped views of the image section, <b>MmFlushImageSection</b> destroys the image section and returns any used pages to the free list. 

Before using <b>MmFlushImageSection</b>, file system writers are strongly encouraged to study the way this routine is used in the FASTFAT sample. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539188">CcPurgeCacheSection</a>
 

 

