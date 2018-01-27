---
UID: NF:ntifs.MmCanFileBeTruncated
title: MmCanFileBeTruncated function
author: windows-driver-content
description: The MmCanFileBeTruncated routine checks whether a file can be truncated.
old-location: ifsk\mmcanfilebetruncated.htm
old-project: ifsk
ms.assetid: 219ecf09-54eb-4972-ae71-0eb3e7ea8ea9
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: mmref_7d6c86f9-4a26-4d2c-bf55-9352044e9339.xml, MmCanFileBeTruncated routine [Installable File System Drivers], ifsk.mmcanfilebetruncated, MmCanFileBeTruncated, ntifs/MmCanFileBeTruncated
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
req.irql: < DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	MmCanFileBeTruncated
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# MmCanFileBeTruncated function


## -description


The <b>MmCanFileBeTruncated</b> routine checks whether a file can be truncated.


## -syntax


````
BOOLEAN MmCanFileBeTruncated(
  _In_     PSECTION_OBJECT_POINTERS SectionPointer,
  _In_opt_ PLARGE_INTEGER           NewFileSize
);
````


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
One or more users hold references to the data section for the file, and <i>NewFileSize</i> &lt;= the current file size.

</li>
</ul>


## -see-also

<a href="..\ntifs\nf-ntifs-mmflushimagesection.md">MmFlushImageSection</a>

<a href="..\ntifs\nf-ntifs-ccpurgecachesection.md">CcPurgeCacheSection</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20MmCanFileBeTruncated routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

