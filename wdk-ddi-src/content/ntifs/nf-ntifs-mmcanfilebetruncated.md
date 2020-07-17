---
UID: NF:ntifs.MmCanFileBeTruncated
title: MmCanFileBeTruncated function (ntifs.h)
description: The MmCanFileBeTruncated routine checks whether a file can be truncated.
old-location: ifsk\mmcanfilebetruncated.htm
tech.root: ifsk
ms.assetid: 219ecf09-54eb-4972-ae71-0eb3e7ea8ea9
ms.date: 04/16/2018
keywords: ["MmCanFileBeTruncated function"]
ms.keywords: MmCanFileBeTruncated, MmCanFileBeTruncated routine [Installable File System Drivers], ifsk.mmcanfilebetruncated, mmref_7d6c86f9-4a26-4d2c-bf55-9352044e9339.xml, ntifs/MmCanFileBeTruncated
f1_keywords:
 - "ntifs/MmCanFileBeTruncated"
 - "MmCanFileBeTruncated"
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
req.irql: < DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmCanFileBeTruncated
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmCanFileBeTruncated function


## -description


The <b>MmCanFileBeTruncated</b> routine checks whether a file can be truncated.


## -parameters




### -param SectionPointer [in]

Pointer to a structure that contains the file object's section object pointers.


### -param NewFileSize [in, optional]

Pointer to a variable that specifies the size to which the file is to be truncated.


## -returns



<b>MmCanFileBeTruncated</b> returns <b>TRUE</b> if the file can be truncated, <b>FALSE</b> otherwise.




## -remarks



<b>MmCanFileBeTruncated</b> must always be called before a file is truncated.

A file cannot be truncated (and <b>MmCanFileBeTruncated</b> will return <b>FALSE</b>) if any of the following are true:

<ul>
<li>
An image section exists for the file.

</li>
<li>
There are one or more outstanding write probes on the file's data section.

</li>
<li>
There is a mapped view of file's data section within the truncation range determined by <i>NewFileSize</i>.

</li>
<li>
One or more users hold references to the data section for the file, and <i>NewFileSize</i> <= the current file size.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539188">CcPurgeCacheSection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-mmflushimagesection">MmFlushImageSection</a>
 

 

