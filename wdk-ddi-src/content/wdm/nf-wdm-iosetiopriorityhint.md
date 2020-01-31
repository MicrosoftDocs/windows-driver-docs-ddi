---
UID: NF:wdm.IoSetIoPriorityHint
title: IoSetIoPriorityHint function (wdm.h)
description: The IoSetIoPriorityHint routine sets the priority hint value for an IRP.
old-location: kernel\iosetiopriorityhint.htm
tech.root: kernel
ms.assetid: ecd4ed14-b9f2-45ff-a42b-5c67f1ccfd91
ms.date: 04/30/2018
ms.keywords: IoSetIoPriorityHint, IoSetIoPriorityHint routine [Kernel-Mode Driver Architecture], k104_9d72dacc-03a6-4dda-8c2b-69b59a817392.xml, kernel.iosetiopriorityhint, wdm/IoSetIoPriorityHint
f1_keywords:
 - "wdm/IoSetIoPriorityHint"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
- IoSetIoPriorityHint
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoSetIoPriorityHint function


## -description


The <b>IoSetIoPriorityHint</b> routine sets the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-irp-priority-hints">priority hint value</a> for an IRP.


## -parameters




### -param Irp [in]

Specifies the IRP to set the priority hint value for.


### -param PriorityHint [in]

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_io_priority_hint">IO_PRIORITY_HINT</a> value that indicates the new priority hint.


## -returns



<b>IoSetIoPriorityHint</b> returns STATUS_SUCCESS if the operation succeeds and the appropriate NTSTATUS value if the operation fails.




## -remarks



For more information about priority hints, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-irp-priority-hints">Using IRP Priority Hints</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_io_priority_hint">IO_PRIORITY_HINT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetiopriorityhint">IoGetIoPriorityHint</a>
 

 

