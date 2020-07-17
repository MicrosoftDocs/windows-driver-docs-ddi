---
UID: NF:wdm.IoGetIoPriorityHint
title: IoGetIoPriorityHint function (wdm.h)
description: The IoGetIoPriorityHint routine gets the priority hint value from an IRP.
old-location: kernel\iogetiopriorityhint.htm
tech.root: kernel
ms.assetid: eddb6cea-74fc-4faf-85fa-3a35d6890802
ms.date: 04/30/2018
keywords: ["IoGetIoPriorityHint function"]
ms.keywords: IoGetIoPriorityHint, IoGetIoPriorityHint routine [Kernel-Mode Driver Architecture], k104_7d622ea7-68a8-4029-96d4-5c40d4f348de.xml, kernel.iogetiopriorityhint, wdm/IoGetIoPriorityHint
f1_keywords:
 - "wdm/IoGetIoPriorityHint"
 - "IoGetIoPriorityHint"
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
- IoGetIoPriorityHint
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoGetIoPriorityHint function


## -description


The <b>IoGetIoPriorityHint</b> routine gets the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-irp-priority-hints">priority hint value</a> from an IRP.


## -parameters




### -param Irp [in]

Specifies the IRP to obtain the priority hint from.


## -returns



<b>IoGetIoPriorityHint</b> returns the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_io_priority_hint">IO_PRIORITY_HINT</a> value that indicates the current priority hint.




## -remarks



For more information about priority hints, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-irp-priority-hints">Using IRP Priority Hints</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_io_priority_hint">IO_PRIORITY_HINT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetiopriorityhint">IoSetIoPriorityHint</a>
 

 

