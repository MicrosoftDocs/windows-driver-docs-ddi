---
UID: NF:wdm.KeGetCurrentThread
title: KeGetCurrentThread function (wdm.h)
description: The KeGetCurrentThread routine identifies the current thread.
old-location: kernel\kegetcurrentthread.htm
tech.root: kernel
ms.assetid: 0fbc9f6d-698b-4fa5-86c4-3f6ef0cc50fb
ms.date: 04/30/2018
keywords: ["KeGetCurrentThread function"]
ms.keywords: KeGetCurrentThread, KeGetCurrentThread routine [Kernel-Mode Driver Architecture], k105_fa2d3ae9-9ac8-4c50-bf51-5d6751a2b81e.xml, kernel.kegetcurrentthread, wdm/KeGetCurrentThread
f1_keywords:
 - "wdm/KeGetCurrentThread"
 - "KeGetCurrentThread"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
- KeGetCurrentThread
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeGetCurrentThread function


## -description


The <b>KeGetCurrentThread</b> routine identifies the current thread. 


## -returns



<b>KeGetCurrentThread</b> returns a pointer to an opaque thread object. 




## -remarks



This routine is identical to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentthread">PsGetCurrentThread</a>.

A caller of <b>KeGetCurrentThread</b> can use the returned pointer as an input parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequeryprioritythread">KeQueryPriorityThread</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kesetbaseprioritythread">KeSetBasePriorityThread</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetprioritythread">KeSetPriorityThread</a>. However, the memory containing the thread object is opaque; that is, it is reserved for exclusive use by the operating system.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequeryprioritythread">KeQueryPriorityThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kesetbaseprioritythread">KeSetBasePriorityThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetprioritythread">KeSetPriorityThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentthread">PsGetCurrentThread</a>
 

 

