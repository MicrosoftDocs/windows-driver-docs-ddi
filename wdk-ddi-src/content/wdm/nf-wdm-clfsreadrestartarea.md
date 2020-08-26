---
UID: NF:wdm.ClfsReadRestartArea
title: ClfsReadRestartArea function (wdm.h)
description: The ClfsReadRestartArea routine reads the restart record that was most recently written to a specified CLFS stream.
old-location: kernel\clfsreadrestartarea.htm
tech.root: kernel
ms.assetid: d391a7ed-220e-412a-8e32-22b206c7a062
ms.date: 04/30/2018
keywords: ["ClfsReadRestartArea function"]
ms.keywords: ClfsReadRestartArea, ClfsReadRestartArea routine [Kernel-Mode Driver Architecture], Clfs_bce9c012-cc19-472e-a1b3-c2d83435c6c0.xml, kernel.clfsreadrestartarea, wdm/ClfsReadRestartArea
f1_keywords:
 - "wdm/ClfsReadRestartArea"
 - "ClfsReadRestartArea"
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
- ClfsReadRestartArea
targetos: Windows
req.typenames: 
---

# ClfsReadRestartArea function


## -description


The <b>ClfsReadRestartArea</b> routine reads the restart record that was most recently written to a specified CLFS stream.


## -parameters




### -param pvMarshalContext 
[in, out]
A pointer to an opaque context that represents a marshalling area associated with a CLFS stream. The caller previously obtained this pointer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatemarshallingarea">ClfsCreateMarshallingArea</a>.


### -param ppvRestartBuffer 
[out]
A pointer to a variable that receives a pointer to the data buffer of the restart record.


### -param pcbRestartBuffer 
[out]
A pointer to a ULONG-typed variable that receives the size, in bytes, of the data buffer pointed to by <i>pcbRestartBuffer</i>. This is the length of the data buffer of the restart record.


### -param plsn 
[out]
A pointer to a CLFS_LSN structure that receives the LSN of the restart record that was read.


### -param ppvReadContext 
[out]
A pointer to a variable that receives a pointer to an opaque read context. The caller can pass this context to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsreadpreviousrestartarea">ClfsReadPreviousRestartArea</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsreadnextlogrecord">ClfsReadNextLogRecord</a>. When the caller has finished using the read context, it must free the context by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsterminatereadlog">ClfsTerminateReadLog</a>.


## -returns



<b>ClfsReadRestartArea</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>.

For information about reading records from CLFS streams, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/reading-data-records-from-a-clfs-stream">Reading Data Records from a CLFS Stream</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/reading-restart-records-from-a-clfs-stream">Reading Restart Records from a CLFS Stream</a>.

Read contexts are not thread-safe. Clients are responsible for serializing access to read contexts. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatemarshallingarea">ClfsCreateMarshallingArea</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsreadnextlogrecord">ClfsReadNextLogRecord</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsreadpreviousrestartarea">ClfsReadPreviousRestartArea</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsterminatereadlog">ClfsTerminateReadLog</a>
 

 

