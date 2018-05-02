---
UID: NF:wdm.IoGetIoPriorityHint
title: IoGetIoPriorityHint function
author: windows-driver-content
description: The IoGetIoPriorityHint routine gets the priority hint value from an IRP.
old-location: kernel\iogetiopriorityhint.htm
old-project: kernel
ms.assetid: eddb6cea-74fc-4faf-85fa-3a35d6890802
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: IoGetIoPriorityHint, IoGetIoPriorityHint routine [Kernel-Mode Driver Architecture], k104_7d622ea7-68a8-4029-96d4-5c40d4f348de.xml, kernel.iogetiopriorityhint, wdm/IoGetIoPriorityHint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoGetIoPriorityHint
product: Windows
targetos: Windows
req.typenames: 
---

# IoGetIoPriorityHint function


## -description


The <b>IoGetIoPriorityHint</b> routine gets the <a href="https://msdn.microsoft.com/c34afff2-32f2-451b-ab16-ff048d5c3204">priority hint value</a> from an IRP.


## -parameters




### -param Irp [in]

Specifies the IRP to obtain the priority hint from.


## -returns



<b>IoGetIoPriorityHint</b> returns the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550594">IO_PRIORITY_HINT</a> value that indicates the current priority hint.




## -remarks



For more information about priority hints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565403">Using IRP Priority Hints</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550594">IO_PRIORITY_HINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549710">IoSetIoPriorityHint</a>
 

 

