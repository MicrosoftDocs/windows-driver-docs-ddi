---
UID: NF:wdm.ClfsAdvanceLogBase
title: ClfsAdvanceLogBase function (wdm.h)
description: The ClfsAdvanceLogBase routine sets the base LSN of a CLFS stream.
old-location: kernel\clfsadvancelogbase.htm
tech.root: kernel
ms.assetid: 00f776f7-83c5-4856-a1d3-8b76122d3986
ms.date: 04/30/2018
ms.keywords: ClfsAdvanceLogBase, ClfsAdvanceLogBase routine [Kernel-Mode Driver Architecture], Clfs_d8f1a522-ef50-47fe-bd39-f18f2f176a3b.xml, kernel.clfsadvancelogbase, wdm/ClfsAdvanceLogBase
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
-	ClfsAdvanceLogBase
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsAdvanceLogBase function


## -description


The <b>ClfsAdvanceLogBase</b> routine sets the base LSN of a CLFS stream.


## -parameters




### -param pvMarshalContext [in, out]

A pointer to an opaque context that represents a marshalling area associated with a CLFS stream. The caller previously obtained this pointer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541520">ClfsCreateMarshallingArea</a>.


### -param plsnBase [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541824">CLFS_LSN</a> structure that contains the new base LSN. This parameter must be the LSN of one of the records in the stream. Also, this parameter must be greater than or equal to the stream's current base LSN and less than or equal to the stream's current last LSN.


### -param fFlags [in]

This parameter is reserved for system use. Callers must set this parameter to zero.


## -returns



<b>ClfsAdvanceLogBase</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



<b>ClfsAdvanceLogBase</b> does not write any records to the CLFS log; the only updates to the log are in the metadata. If you want to update the base LSN and write a restart record to a stream at the same time, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff541770">ClfsWriteRestartArea</a>.

Whenever possible, CLFS avoids writing queued log records that have LSNs less than the new base LSN to stable storage.

<b>ClfsAdvanceLogBase</b> does not check to see whether the LSN supplied in <i>plsnBase</i> is actually the LSN of one of the records in the stream. If the caller sets <i>plsnBase</i> to an LSN that is not the LSN of one of the records in the stream, the stream's base LSN will be set to a meaningless value.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541770">ClfsWriteRestartArea</a>
 

 

