---
UID: NF:wdm.ClfsFlushBuffers
title: ClfsFlushBuffers function (wdm.h)
description: The ClfsFlushBuffers routine forces all log I/O blocks in a specified marshalling area to stable storage.
old-location: kernel\clfsflushbuffers.htm
tech.root: kernel
ms.assetid: 70e93c8f-a23c-4399-9299-c2743d097ded
ms.date: 04/30/2018
keywords: ["ClfsFlushBuffers function"]
ms.keywords: ClfsFlushBuffers, ClfsFlushBuffers routine [Kernel-Mode Driver Architecture], Clfs_3c04240c-0914-472f-9b4b-97a00221e092.xml, kernel.clfsflushbuffers, wdm/ClfsFlushBuffers
f1_keywords:
 - "wdm/ClfsFlushBuffers"
 - "ClfsFlushBuffers"
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
- ClfsFlushBuffers
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsFlushBuffers function


## -description


The <b>ClfsFlushBuffers</b> routine forces all log I/O blocks in a specified marshalling area to stable storage.


## -parameters




### -param pvMarshalContext [in]

A pointer to an opaque context that represents a marshalling area. The caller previously obtained this pointer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatemarshallingarea">ClfsCreateMarshallingArea</a>.


## -returns



<b>ClfsFlushBuffers</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



Calling <b>ClfsFlushBuffers</b> is equivalent to calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsflushtolsn">ClfsFlushToLsn</a> with the <i>plsnFlush</i> parameter set to CLFS_LSN_NULL.

For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsflushtolsn">ClfsFlushToLsn</a>
 

 

