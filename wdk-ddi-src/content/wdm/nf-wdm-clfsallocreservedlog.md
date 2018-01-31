---
UID: NF:wdm.ClfsAllocReservedLog
title: ClfsAllocReservedLog function
author: windows-driver-content
description: The ClfsAllocReservedLog routine reserves space in a marshalling area for a set of records.
old-location: kernel\clfsallocreservedlog.htm
old-project: kernel
ms.assetid: 05e4fb47-38ef-4b46-a1bb-220c5b1a63ca
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: Clfs_4429c61b-96d5-48cb-9ff0-5b0e3f01e0ec.xml, ClfsAllocReservedLog routine [Kernel-Mode Driver Architecture], wdm/ClfsAllocReservedLog, kernel.clfsallocreservedlog, ClfsAllocReservedLog
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
-	ClfsAllocReservedLog
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsAllocReservedLog function


## -description


The <b>ClfsAllocReservedLog</b> routine reserves space in a marshalling area for a set of records.


## -syntax


````
NTSTATUS ClfsAllocReservedLog(
  _In_ PVOID     pvMarshalContext,
  _In_ ULONG     cRecords,
  _In_ PLONGLONG pcbAdjustment
);
````


## -parameters




#### - pvMarshalContext [in]

A pointer to an opaque context that represents a marshalling area. The caller previously obtained this pointer by calling <a href="..\wdm\nf-wdm-clfscreatemarshallingarea.md">ClfsCreateMarshallingArea</a>.


#### - cRecords [in]

The number of records in the set. This value must match the value of <i>cRecords</i> previously passed to <a href="..\wdm\nf-wdm-clfsalignreservedlog.md">ClfsAlignReservedLog</a>.


#### - pcbAdjustment [in]

A pointer to a LONGLONG-typed variable that supplies the size, in bytes, of the reservation that will hold all the records in the set. The caller previously obtained this size by calling <a href="..\wdm\nf-wdm-clfsalignreservedlog.md">ClfsAlignReservedLog</a>.


## -returns


<b>ClfsAllocReservedLog</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.



## -remarks


For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.



## -see-also

<a href="..\wdm\nf-wdm-clfsalignreservedlog.md">ClfsAlignReservedLog</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsAllocReservedLog routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

