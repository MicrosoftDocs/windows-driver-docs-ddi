---
UID: NF:wdm.ClfsReserveAndAppendLogAligned
title: ClfsReserveAndAppendLogAligned function (wdm.h)
description: The ClfsReserveAndAppendLogAligned routine reserves space in a marshalling area or appends a record to a marshalling area or does both atomically. The record's data is aligned on specified boundaries.
old-location: kernel\clfsreserveandappendlogaligned.htm
tech.root: kernel
ms.assetid: 4502c9bd-d03c-4f29-b46e-ba4532b838bb
ms.date: 04/30/2018
ms.keywords: ClfsReserveAndAppendLogAligned, ClfsReserveAndAppendLogAligned routine [Kernel-Mode Driver Architecture], Clfs_aef34ba7-9276-41a4-8136-b20ae8e8531d.xml, kernel.clfsreserveandappendlogaligned, wdm/ClfsReserveAndAppendLogAligned
ms.topic: function
f1_keywords:
 - "wdm/ClfsReserveAndAppendLogAligned"
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
- ClfsReserveAndAppendLogAligned
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsReserveAndAppendLogAligned function


## -description


The <b>ClfsReserveAndAppendLogAligned</b> routine reserves space in a marshalling area or appends a record to a marshalling area or does both atomically. The record's data is aligned on specified boundaries.


## -parameters




### -param pvMarshalContext [in]

A pointer to an opaque context that represents a marshalling area associated with a CLFS stream. The caller previously obtained this pointer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatemarshallingarea">ClfsCreateMarshallingArea</a>.


### -param rgWriteEntries [in, optional]

A pointer to an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_write_entry">CLFS_WRITE_ENTRY</a> structures, each of which holds a pointer to a buffer of data that will become part of the record that is appended to the log. This parameter can be <b>NULL</b> if <i>cWriteEntries</i> is zero.


### -param cWriteEntries [in]

The number of elements in the array pointed to by <i>rgWriteEntries</i>. This parameter must be zero if <i>rgWriteEntries</i> is <b>NULL</b>.


### -param cbEntryAlignment [in]

The byte alignment of the data entries pointed to by <i>rgWriteEntries</i> as they are marshaled into a single record. A value of one specifies simple concatenation (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsreserveandappendlog">ClfsReserveAndAppendLog</a>). A value larger than one can result in zeros being placed between entries in the record. The value of this parameter must be greater than zero.


### -param plsnUndoNext [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_lsn">CLFS_LSN</a> structure that supplies the undo-next LSN of the record to be appended.


### -param plsnPrevious [in, optional]

A pointer to a CLFS_LSN structure that supplies the previous LSN of the record to be appended.


### -param cReserveRecords [in]

The number of elements in the array pointed to by <i>rgcbReservation</i>. This parameter must be zero if <i>rgcbReservation</i> is <b>NULL</b> or the CLFS_FLAG_USE_RESERVATION flag of <i>fFlags</i> is set.


### -param rgcbReservation [in, out]

A pointer to an array of LONGLONG-typed variables. The caller sets each element of the array to the size, in bytes, of a record that must have space reserve for it. On return, each array element receives that actual size of the space reserved for the record. This includes the space required for headers and alignment. If the reservation value is negative, a reserved record that most nearly matches the absolute value of the provided negative value will be freed. This parameter can be <b>NULL</b> if <i>cReserveRecords</i> is zero and must be <b>NULL</b> if the CLFS_FLAG_USE_RESERVATION flag of <i>fFlags</i> is set.


### -param fFlags [in]

This parameter can be any combination of the following flags.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
CLFS_FLAG_FORCE_APPEND

</td>
<td>
After the current record is appended to a log I/O block, the block is queued, in LSN sequence, to stable storage. This flag provides no guarantee that the record is forced to stable storage (see CLFS_FLAG_FORCE_FLUSH).

</td>
</tr>
<tr>
<td>
CLFS_FLAG_FORCE_FLUSH

</td>
<td>
After the current record is appended to a log I/O block, the block is forced to stable storage.

</td>
</tr>
<tr>
<td>
CLFS_FLAG_USE_RESERVATION

</td>
<td>
The current record is placed in reserved space in an I/O block. The number of reserved records in the marshalling area is reduced by one. If this flag is set, <i>cReserveRecords</i> must be zero and <i>rgcbReservation</i> must be <b>NULL</b>.

</td>
</tr>
</table>
 


### -param plsn [out, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_lsn">CLFS_LSN</a> structure that receives the LSN of the appended record. This parameter can be <b>NULL</b> if <i>cWriteEntries</i> is zero.


## -returns



<b>ClfsReserveAndAppendLogAligned</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



The <b>ClfsReserveAndAppendLogAligned</b> routine changes its fundamental behavior based on the presence of optional parameters and the state of the CLFS_USE_RESERVATION flag. The following table summarizes common scenarios.

<table>
<tr>
<th>Parameter and flag values</th>
<th>Actions performed</th>
</tr>
<tr>
<td>
<i>cWriteEntries</i> = 0.

<i>rgWriteEntries</i> = <b>NULL</b>.

<i>plsn</i> = <b>NULL</b>.

</td>
<td>
Reserves space for a set of records, but does not append the records to the marshalling area. The <i>rgcbReservation</i> parameter gives the size of the data portion of each record that needs space reserved.

</td>
</tr>
<tr>
<td>
<i>cWriteEntries</i> > 0.

<i>rgWriteEntries</i> is not <b>NULL</b>.

<i>plsn</i> is not <b>NULL</b>.

<i>cReserveRecords</i> = 0.

<i>rgcbReservation</i> is <b>NULL</b>.

CLFS_USE_RESERVATION is set.

</td>
<td>
Appends a record to the marshalling area by using space that has already been reserved. Reduces the number of reserved record spaces by one.

</td>
</tr>
<tr>
<td>
<i>cWriteEntries</i> > 0.

<i>rgWriteEntries</i> is not <b>NULL</b>.

<i>plsn</i> is not <b>NULL</b>.

<i>cReserveRecords</i> = 0.

<i>rgcbReservation</i> is <b>NULL</b>.

CLFS_USE_RESERVATION is cleared.

</td>
<td>
Appends a record to the marshalling area by reserving new space. Leaves the number of reserved record spaces unchanged.

</td>
</tr>
<tr>
<td>
<i>cWriteEntries</i> > 0.

<i>rgWriteEntries</i> is not <b>NULL</b>.

<i>plsn</i> is not <b>NULL</b>.

<i>cReserveRecords</i> > 0.

<i>rgcbReservation</i> is not <b>NULL</b>.

CLFS_USE_RESERVATION flag is cleared.

</td>
<td>
Appends a record to the marshalling area by reserving new space. Also reserves space for a set of records that are not appended at this time. The <i>rgcbReservation</i> parameter gives the size of each record that needs space reserved. Increases the number of reserved record spaces by the value of <i>cReserveRecords</i>.

</td>
</tr>
</table>
 

For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_lsn">CLFS_LSN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cls_write_entry">CLFS_WRITE_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatemarshallingarea">ClfsCreateMarshallingArea</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsreserveandappendlog">ClfsReserveAndAppendLog</a>
 

 

