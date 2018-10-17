---
UID: NF:ntddk.IoGetPagingIoPriority
title: IoGetPagingIoPriority function
author: windows-driver-content
description: The IoGetPagingIoPriority routine indicates the priority level of a paging I/O request.
old-location: kernel\iogetpagingiopriority.htm
tech.root: kernel
ms.assetid: 3b0f4fc9-58fd-46ba-be17-2e1b36b16caa
ms.date: 4/30/2018
ms.keywords: IoGetPagingIoPriority, IoGetPagingIoPriority routine [Kernel-Mode Driver Architecture], k104_cde35790-d059-44bb-85c5-abde7cb36319.xml, kernel.iogetpagingiopriority, wdm/IoGetPagingIoPriority
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoGetPagingIoPriority
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoGetPagingIoPriority function


## -description


The <b>IoGetPagingIoPriority</b> routine indicates the priority level of a paging I/O request.


## -parameters




### -param Irp [in]

Pointer to the IRP to be tested for paging priority.


## -returns



<b>IoGetPagingIoPriority</b> returns the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550590">IO_PAGING_PRIORITY</a> value for the associated IRP.




## -remarks



For I/O requests that causing paging, the system associates an <b>IO_PAGING_PRIORITY</b> value that describes the IRP's priority. Drivers can use this value when queuing IRPs.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550590">IO_PAGING_PRIORITY</a>
 

 

