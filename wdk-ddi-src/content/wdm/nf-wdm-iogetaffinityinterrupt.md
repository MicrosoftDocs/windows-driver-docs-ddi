---
UID: NF:wdm.IoGetAffinityInterrupt
title: IoGetAffinityInterrupt function
author: windows-driver-content
description: For more information, see the WdmlibIoGetAffinityInterrupt function.#define IoGetAffinityInterrupt WdmlibIoGetAffinityInterrupt
old-location: kernel\iogetaffinityinterrupt.htm
old-project: kernel
ms.assetid: aec1ace6-9945-4e7a-b0f6-81591670ecfe
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, G, I, IoGetAffinityInterrupt, IoGetAffinityInterrupt routine [Kernel-Mode Driver Architecture], WdmlibIoGetAffinityInterrupt, e, f, i, k104_39247b69-50e1-4162-b26e-81b5358738de.xml, kernel.iogetaffinityinterrupt, n, o, p, r, t, u, wdm/IoGetAffinityInterrupt, wdm/WdmlibIoGetAffinityInterrupt, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	IoGetAffinityInterrupt
-	WdmlibIoGetAffinityInterrupt
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoGetAffinityInterrupt function


## -description


For more information, see the <a href="..\iointex\nf-iointex-wdmlibiogetaffinityinterrupt.md">WdmlibIoGetAffinityInterrupt</a> function.

<code>#define IoGetAffinityInterrupt WdmlibIoGetAffinityInterrupt</code>


## -syntax


````
NTSTATUS IoGetAffinityInterrupt(
  _In_  PKINTERRUPT     InterruptObject,
  _Out_ PGROUP_AFFINITY GroupAffinity
);
````


## -parameters




### -param InterruptObject [in]

For more information, see the <a href="..\iointex\nf-iointex-wdmlibiogetaffinityinterrupt.md">WdmlibIoGetAffinityInterrupt</a> function.


### -param GroupAffinity [out]

For more information, see the <a href="..\iointex\nf-iointex-wdmlibiogetaffinityinterrupt.md">WdmlibIoGetAffinityInterrupt</a> function.


## -returns



For more information, see the <a href="..\iointex\nf-iointex-wdmlibiogetaffinityinterrupt.md">WdmlibIoGetAffinityInterrupt</a> function.




## -see-also

<a href="..\iointex\nf-iointex-wdmlibiogetaffinityinterrupt.md">WdmlibIoGetAffinityInterrupt</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetAffinityInterrupt routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

