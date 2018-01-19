---
UID: NF:wdm.ClfsAdvanceLogBase
title: ClfsAdvanceLogBase function
author: windows-driver-content
description: The ClfsAdvanceLogBase routine sets the base LSN of a CLFS stream.
old-location: kernel\clfsadvancelogbase.htm
old-project: kernel
ms.assetid: 00f776f7-83c5-4856-a1d3-8b76122d3986
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ClfsAdvanceLogBase
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
req.alt-api: ClfsAdvanceLogBase
req.alt-loc: Clfs.sys,Ext-MS-Win-fs-clfs-l1-1-0.dll
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsAdvanceLogBase function



## -description
The <b>ClfsAdvanceLogBase</b> routine sets the base LSN of a CLFS stream.



## -syntax

````
NTSTATUS ClfsAdvanceLogBase(
  _Inout_ PVOID     pvMarshalContext,
  _In_    PCLFS_LSN plsnBase,
  _In_    ULONG     fFlags
);
````


## -parameters

### -param pvMarshalContext [in, out]

A pointer to an opaque context that represents a marshalling area associated with a CLFS stream. The caller previously obtained this pointer by calling <a href="..\wdm\nf-wdm-clfscreatemarshallingarea.md">ClfsCreateMarshallingArea</a>.


### -param plsnBase [in]

A pointer to a <a href="..\wdm\ns-wdm-_cls_lsn.md">CLFS_LSN</a> structure that contains the new base LSN. This parameter must be the LSN of one of the records in the stream. Also, this parameter must be greater than or equal to the stream's current base LSN and less than or equal to the stream's current last LSN.


### -param fFlags [in]

This parameter is reserved for system use. Callers must set this parameter to zero.


## -returns
<b>ClfsAdvanceLogBase</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.


## -remarks
<b>ClfsAdvanceLogBase</b> does not write any records to the CLFS log; the only updates to the log are in the metadata. If you want to update the base LSN and write a restart record to a stream at the same time, call <a href="..\wdm\nf-wdm-clfswriterestartarea.md">ClfsWriteRestartArea</a>.

Whenever possible, CLFS avoids writing queued log records that have LSNs less than the new base LSN to stable storage.

<b>ClfsAdvanceLogBase</b> does not check to see whether the LSN supplied in <i>plsnBase</i> is actually the LSN of one of the records in the stream. If the caller sets <i>plsnBase</i> to an LSN that is not the LSN of one of the records in the stream, the stream's base LSN will be set to a meaningless value.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-clfswriterestartarea.md">ClfsWriteRestartArea</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsAdvanceLogBase routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

