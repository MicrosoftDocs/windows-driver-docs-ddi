---
UID: NF:wdm.ClfsReadRestartArea
title: ClfsReadRestartArea function
author: windows-driver-content
description: The ClfsReadRestartArea routine reads the restart record that was most recently written to a specified CLFS stream.
old-location: kernel\clfsreadrestartarea.htm
old-project: kernel
ms.assetid: d391a7ed-220e-412a-8e32-22b206c7a062
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: Clfs_bce9c012-cc19-472e-a1b3-c2d83435c6c0.xml, ClfsReadRestartArea routine [Kernel-Mode Driver Architecture], wdm/ClfsReadRestartArea, ClfsReadRestartArea, kernel.clfsreadrestartarea
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
req.irql: <= APC_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
apiname: 
-	ClfsReadRestartArea
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsReadRestartArea function


## -description


The <b>ClfsReadRestartArea</b> routine reads the restart record that was most recently written to a specified CLFS stream.


## -syntax


````
NTSTATUS ClfsReadRestartArea(
  _Inout_ PVOID     pvMarshalContext,
  _Out_   PVOID     *ppvRestartBuffer,
  _Out_   PULONG    pcbRestartBuffer,
  _Out_   PCLFS_LSN plsn,
  _Out_   PVOID     *ppvReadContext
);
````


## -parameters




### -param pvMarshalContext [in, out]

A pointer to an opaque context that represents a marshalling area associated with a CLFS stream. The caller previously obtained this pointer by calling <a href="..\wdm\nf-wdm-clfscreatemarshallingarea.md">ClfsCreateMarshallingArea</a>.


### -param ppvRestartBuffer [out]

A pointer to a variable that receives a pointer to the data buffer of the restart record.


### -param pcbRestartBuffer [out]

A pointer to a ULONG-typed variable that receives the size, in bytes, of the data buffer pointed to by <i>pcbRestartBuffer</i>. This is the length of the data buffer of the restart record.


### -param plsn [out]

A pointer to a CLFS_LSN structure that receives the LSN of the restart record that was read.


### -param ppvReadContext [out]

A pointer to a variable that receives a pointer to an opaque read context. The caller can pass this context to <a href="..\wdm\nf-wdm-clfsreadpreviousrestartarea.md">ClfsReadPreviousRestartArea</a> or <a href="..\wdm\nf-wdm-clfsreadnextlogrecord.md">ClfsReadNextLogRecord</a>. When the caller has finished using the read context, it must free the context by calling <a href="..\wdm\nf-wdm-clfsterminatereadlog.md">ClfsTerminateReadLog</a>.


## -returns


<b>ClfsReadRestartArea</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.



## -remarks


For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.

For information about reading records from CLFS streams, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560785">Reading Data Records from a CLFS Stream</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff560786">Reading Restart Records from a CLFS Stream</a>.

Read contexts are not thread-safe. Clients are responsible for serializing access to read contexts. 



## -see-also

<a href="..\wdm\nf-wdm-clfsreadpreviousrestartarea.md">ClfsReadPreviousRestartArea</a>

<a href="..\wdm\nf-wdm-clfsterminatereadlog.md">ClfsTerminateReadLog</a>

<a href="..\wdm\nf-wdm-clfsreadnextlogrecord.md">ClfsReadNextLogRecord</a>

<a href="..\wdm\nf-wdm-clfscreatemarshallingarea.md">ClfsCreateMarshallingArea</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsReadRestartArea routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

