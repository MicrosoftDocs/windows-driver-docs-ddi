---
UID: NF:wdm.ClfsReadLogRecord
title: ClfsReadLogRecord function (wdm.h)
description: The ClfsReadLogRecord routine reads a target record in a CLFS stream and returns a read context that the caller can use to read the records preceding or following it in the stream.
old-location: kernel\clfsreadlogrecord.htm
tech.root: kernel
ms.assetid: 9bc64d00-3590-4bc2-aa1f-0d50bb0e628d
ms.date: 04/30/2018
ms.keywords: ClfsReadLogRecord, ClfsReadLogRecord routine [Kernel-Mode Driver Architecture], Clfs_e829153c-541e-463a-9ff3-85200929e3d2.xml, kernel.clfsreadlogrecord, wdm/ClfsReadLogRecord
ms.topic: function
f1_keywords:
 - "wdm/ClfsReadLogRecord"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Clfs.sys
- Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
- ClfsReadLogRecord
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsReadLogRecord function


## -description


The <b>ClfsReadLogRecord</b> routine reads a target record in a CLFS stream and returns a read context that the caller can use to read the records preceding or following it in the stream.


## -parameters




### -param pvMarshalContext [in]

A pointer to an opaque context that represents a marshalling area. The caller previously obtained this pointer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-clfscreatemarshallingarea">ClfsCreateMarshallingArea</a>.


### -param plsnFirst [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_cls_lsn">CLFS_LSN</a> structure that supplies the LSN of the target record in the log.


### -param peContextMode [in]

A value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_clfs_context_mode">CLFS_CONTEXT_MODE</a> enumeration that specifies the initial mode (ClfsContextUndoNext, ClfsContextPrevious, or ClfsContextForward) of the read context returned in <i>ppvReadContext</i>.


### -param ppvReadBuffer [out]

A pointer to a variable that receives a pointer to the data buffer of the target record.


### -param pcbReadBuffer [out]

A pointer to a ULONG-typed variable that receives the size, in bytes, of the buffer pointed to by *<i>ppvReadBuffer</i>. This is the length of the data buffer of the target record.


### -param peRecordType [out]

A pointer to a variable of type CLFS_RECORD_TYPE that receives one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>ClfsDataRecord</b>

</td>
<td>
The target record is a data record.

</td>
</tr>
<tr>
<td>
<b>ClfsRestartRecord</b>

</td>
<td>
The target record is a restart record.

</td>
</tr>
</table>
 


### -param plsnUndoNext [out]

A pointer to a <b>CLFS_LSN</b> structure that receives the undo-next LSN of the target record.


### -param plsnPrevious [out]

A pointer to a <b>CLFS_LSN</b> structure that receives the previous LSN of the target record.


### -param ppvReadContext [out]

A pointer to a variable that receives a pointer to an opaque read context. The client repeatedly passes this context to  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-clfsreadnextlogrecord">ClfsReadNextLogRecord</a> to read the remaining records in a sequence. After the client has read all the records in the sequence, it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-clfsterminatereadlog">ClfsTerminateReadLog</a> to free the read context.


## -returns



<b>ClfsReadLogRecord</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



You must call <b>ClfsTerminateReadLog</b> when you have finished using the read context in order to avoid a memory leak.

For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>.

For information about reading records from CLFS streams, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/reading-data-records-from-a-clfs-stream">Reading Data Records from a CLFS Stream</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/reading-restart-records-from-a-clfs-stream">Reading Restart Records from a CLFS Stream</a>.

Read contexts are not thread-safe. Clients are responsible for serializing access to read contexts. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-clfsreadnextlogrecord">ClfsReadNextLogRecord</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-clfsterminatereadlog">ClfsTerminateReadLog</a>
 

 

