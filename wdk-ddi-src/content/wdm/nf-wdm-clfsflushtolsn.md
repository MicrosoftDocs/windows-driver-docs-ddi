---
UID: NF:wdm.ClfsFlushToLsn
title: ClfsFlushToLsn function
description: The ClfsFlushToLsn routine forces, to stable storage, all records that have an LSN less than or equal to a specified LSN.
old-location: kernel\clfsflushtolsn.htm
tech.root: kernel
ms.assetid: fb7d97d2-8c02-44c8-8cf5-e9c3b3b718bb
ms.date: 04/30/2018
ms.keywords: ClfsFlushToLsn, ClfsFlushToLsn routine [Kernel-Mode Driver Architecture], Clfs_80676b51-aa14-42bf-92ae-d11cf0a694b5.xml, kernel.clfsflushtolsn, wdm/ClfsFlushToLsn
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
-	ClfsFlushToLsn
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsFlushToLsn function


## -description


The <b>ClfsFlushToLsn</b> routine forces, to stable storage, all records that have an LSN less than or equal to a specified LSN.


## -parameters




### -param pvMarshalContext [in]

A pointer to an opaque context associated with a marshalling area. The caller previously obtained this pointer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541520">ClfsCreateMarshallingArea</a>.


### -param plsnFlush [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541824">CLFS_LSN</a> structure. All records that have an LSN less than or equal to <i>plsnFlush</i> are guaranteed to be forced to stable storage. If <i>plsnFlush</i> is equal to CLFS_LSN_NULL, then all records in the marshalling area are forced to stable storage.


### -param plsnLastFlushed [out, optional]

A pointer to a <b>CLFS_LSN</b> structure that receives the LSN of the oldest record that was not flushed. This is the LSN of the record immediately following the last record flushed. 

<div class="alert"><b>Note</b>    On successful return, <i>plsnLastFlushed</i> is greater than the value supplied in <i>plsnFlush</i>. However, <i>plsnLastFlushed</i> does not necessarily point to a record in the stream. For example, if all records in the stream were flushed, <i>plsnLastFlushed</i> is the LSN that will be assigned to the next record written to the stream.</div>
<div> </div>

## -returns



<b>ClfsFlushToLsn</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541544">ClfsFlushBuffers</a>
 

 

