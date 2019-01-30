---
UID: NF:ntifs.IoGetTopLevelIrp
title: IoGetTopLevelIrp function (ntifs.h)
description: The IoGetTopLevelIrp routine returns the value of the TopLevelIrp field of the current thread.
old-location: ifsk\iogettoplevelirp.htm
tech.root: ifsk
ms.assetid: e92685f6-031a-464a-b26a-54bebf7d66b6
ms.date: 04/16/2018
ms.keywords: IoGetTopLevelIrp, IoGetTopLevelIrp routine [Installable File System Drivers], ifsk.iogettoplevelirp, ioref_4826c2a4-5c95-461d-b21c-7e3fca98c0cb.xml, ntifs/IoGetTopLevelIrp
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, Wdm.h
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoGetTopLevelIrp
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoGetTopLevelIrp function


## -description


The <b>IoGetTopLevelIrp</b> routine returns the value of the <b>TopLevelIrp</b> field of the current thread.


## -parameters








## -returns



<b>IoGetTopLevelIrp</b> returns the value of the <b>TopLevelIrp</b> field of the current thread.




## -remarks



<b>IoGetTopLevelIrp</b> can return <b>NULL</b>, an arbitrary file-system-specific value (such as a pointer to the current IRP), or one of the flags listed in the following table.

If the current thread holds no resources above the file system, <b>IoGetTopLevelIrp</b> returns <b>NULL</b>.

If the file system is the top-level component for the current thread, <b>IoGetTopLevelIrp</b> returns a pointer to the current IRP.

If a component other than the file system is the top-level component for the current thread, <b>IoGetTopLevelIrp</b> returns one of the following flags: 

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FSRTL_FSP_TOP_LEVEL_IRP

</td>
<td>
This is a recursive call.

</td>
</tr>
<tr>
<td>
FSRTL_CACHE_TOP_LEVEL_IRP

</td>
<td>
The cache manager is the top-level component for the current thread.

</td>
</tr>
<tr>
<td>
FSRTL_MOD_WRITE_TOP_LEVEL_IRP

</td>
<td>
The modified page writer is the top-level component for the current thread.

</td>
</tr>
<tr>
<td>
FSRTL_FAST_IO_TOP_LEVEL_IRP

</td>
<td>
The cache manager is the top-level component for the current thread, and the current thread is in a fast I/O path.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548540">IoSetTopLevelIrp</a>
 

 

