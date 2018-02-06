---
UID: NF:wdm.ClfsWriteRestartArea
title: ClfsWriteRestartArea function
author: windows-driver-content
description: The ClfsWriteRestartArea routine atomically appends a new restart record to a CLFS stream, flushes the restart record to stable storage, and optionally updates the base LSN of the stream.
old-location: kernel\clfswriterestartarea.htm
old-project: kernel
ms.assetid: e97006e1-5a18-4478-9cac-30eb70142fa7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ClfsWriteRestartArea, Clfs_b2bfac14-eb9c-4323-af79-ab8bebf06f79.xml, kernel.clfswriterestartarea, wdm/ClfsWriteRestartArea, ClfsWriteRestartArea routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
apiname:
-	ClfsWriteRestartArea
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsWriteRestartArea function


## -description


The <b>ClfsWriteRestartArea</b> routine atomically appends a new restart record to a CLFS stream, flushes the restart record to stable storage, and optionally updates the base LSN of the stream.


## -syntax


````
NTSTATUS ClfsWriteRestartArea(
  _Inout_   PVOID     pvMarshalContext,
  _In_      PVOID     pvRestartBuffer,
  _In_      ULONG     cbRestartBuffer,
  _In_opt_  PCLFS_LSN plsnBase,
  _In_      ULONG     fFlags,
  _Out_opt_ PULONG    pcbWritten,
  _Out_opt_ PCLFS_LSN plsnNext
);
````


## -parameters




### -param pvMarshalContext [in, out]

A pointer to an opaque context that represents a marshalling area associated with a CLFS stream. The caller previously obtained this pointer by calling <a href="..\wdm\nf-wdm-clfscreatemarshallingarea.md">ClfsCreateMarshallingArea</a>.


### -param pvRestartBuffer [in]

A pointer to a buffer that contains the data for the restart record.


### -param cbRestartBuffer [in]

The size, in bytes, of the buffer pointed to by <i>pvRestartBuffer</i>. This is the size of the restart data.


### -param plsnBase [in, optional]

A pointer to a <a href="..\wdm\ns-wdm-_cls_lsn.md">CLFS_LSN</a> structure that specifies a new base LSN for the stream. If this parameter is <b>NULL</b>, the base LSN is not changed.


### -param fFlags [in]

This parameter must be one of the following values.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0

</td>
<td>
The restart record is placed in newly allocated space in an I/O block. The number of reserved records in the marshalling area is not changed.

</td>
</tr>
<tr>
<td>
CLFS_FLAG_USE_RESERVATION

</td>
<td>
The restart record is placed in previously reserved space in an I/O block. The number of reserved records in the marshalling area is reduced by one.

</td>
</tr>
</table> 


### -param pcbWritten [out, optional]

A pointer to a ULONG-typed variable that receives the number of bytes actually forced to stable storage. This parameter can be <b>NULL</b>.


### -param plsnNext [out, optional]

A pointer to a <b>CLFS_LSN</b> structure that receives the LSN of the newly written restart record.


## -returns


<b>ClfsWriteRestartArea</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.



## -remarks


Typically ClfsWriteRestartArea is called as the last act of a client checkpoint.

ClfsWriteRestartArea is a relatively expensive operation because it causes a flush of all records currently in the marshalling area along with a flush of stream and log metadata.

At any one time, only one marshalling area should be used to write data to a stream. Having two marshalling areas writing into the stream might result in stream corruption.

If you just want to set the base LSN of a stream, use <a href="..\wdm\nf-wdm-clfsadvancelogbase.md">ClfsAdvanceLogBase</a>, which does not necessarily flush any data to stable storage.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 



## -see-also

<a href="..\wdm\nf-wdm-clfsreadpreviousrestartarea.md">ClfsReadPreviousRestartArea</a>

<a href="..\wdm\nf-wdm-clfsadvancelogbase.md">ClfsAdvanceLogBase</a>

<a href="..\wdm\nf-wdm-clfsreadrestartarea.md">ClfsReadRestartArea</a>

<a href="..\wdm\nf-wdm-clfscreatemarshallingarea.md">ClfsCreateMarshallingArea</a>

<a href="..\wdm\ns-wdm-_cls_lsn.md">CLFS_LSN</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsWriteRestartArea routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

