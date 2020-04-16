---
UID: NF:wdm.IoSizeofWorkItem
title: IoSizeofWorkItem function (wdm.h)
description: The IoSizeofWorkItem routine returns the size, in bytes, of an IO_WORKITEM structure.
old-location: kernel\iosizeofworkitem.htm
tech.root: kernel
ms.assetid: 389f0776-1010-4f3c-b5c5-b8807ff07130
ms.date: 04/30/2018
keywords: ["IoSizeofWorkItem function"]
ms.keywords: IoSizeofWorkItem, IoSizeofWorkItem routine [Kernel-Mode Driver Architecture], k104_9f2b3349-cd46-48ec-bcff-10e91bd522b5.xml, kernel.iosizeofworkitem, wdm/IoSizeofWorkItem
f1_keywords:
 - "wdm/IoSizeofWorkItem"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoSizeofWorkItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoSizeofWorkItem function


## -description


The <b>IoSizeofWorkItem</b> routine returns the size, in bytes, of an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_WORKITEM</a> structure. 


## -returns



<b>IoSizeofWorkItem</b> returns the number of bytes necessary to hold an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_WORKITEM</a> structure.




## -remarks



For more information about work items, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-worker-threads">System Worker Threads</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_WORKITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializeworkitem">IoInitializeWorkItem</a>
 

 

