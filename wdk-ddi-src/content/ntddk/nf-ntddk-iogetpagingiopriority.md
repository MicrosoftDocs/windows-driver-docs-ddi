---
UID: NF:ntddk.IoGetPagingIoPriority
title: IoGetPagingIoPriority function
author: windows-driver-content
description: The IoGetPagingIoPriority routine indicates the priority level of a paging I/O request.
old-location: kernel\iogetpagingiopriority.htm
old-project: kernel
ms.assetid: 3b0f4fc9-58fd-46ba-be17-2e1b36b16caa
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoGetPagingIoPriority, IoGetPagingIoPriority routine [Kernel-Mode Driver Architecture], k104_cde35790-d059-44bb-85c5-abde7cb36319.xml, wdm/IoGetPagingIoPriority, kernel.iogetpagingiopriority
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows Server 2003 and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoGetPagingIoPriority
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoGetPagingIoPriority function


## -description


The <b>IoGetPagingIoPriority</b> routine indicates the priority level of a paging I/O request.


## -syntax


````
IO_PAGING_PRIORITY IoGetPagingIoPriority(
  _In_ PIRP Irp
);
````


## -parameters




#### - Irp [in]

Pointer to the IRP to be tested for paging priority.


## -returns


<b>IoGetPagingIoPriority</b> returns the <a href="..\wdm\ne-wdm-_io_paging_priority.md">IO_PAGING_PRIORITY</a> value for the associated IRP.



## -remarks


For I/O requests that causing paging, the system associates an <b>IO_PAGING_PRIORITY</b> value that describes the IRP's priority. Drivers can use this value when queuing IRPs.



## -see-also

<a href="..\wdm\ne-wdm-_io_paging_priority.md">IO_PAGING_PRIORITY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetPagingIoPriority routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

