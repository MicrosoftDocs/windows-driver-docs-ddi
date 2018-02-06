---
UID: NF:wdm.KeSetSystemAffinityThread
title: KeSetSystemAffinityThread function
author: windows-driver-content
description: The KeSetSystemAffinityThread routine sets the system affinity of the current thread.
old-location: kernel\kesetsystemaffinitythread.htm
old-project: kernel
ms.assetid: eb66ed06-356d-4550-8ccf-10854e4ca259
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeSetSystemAffinityThread routine [Kernel-Mode Driver Architecture], kernel.kesetsystemaffinitythread, wdm/KeSetSystemAffinityThread, KeSetSystemAffinityThread, k105_86ff0d26-a53d-4da4-b776-35ed30b950ad.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows. Use KeSetSystemAffinityThread only on systems before Windows Vista. In Windows Vista and later versions of the Windows operating system, use KeSetSystemAffinityThreadEx instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL (see Remarks section)."
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeSetSystemAffinityThread
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeSetSystemAffinityThread function


## -description


The <b>KeSetSystemAffinityThread</b> routine sets the system affinity of the current thread.


## -syntax


````
VOID KeSetSystemAffinityThread(
  _In_ KAFFINITY Affinity
);
````


## -parameters




### -param Affinity [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>-typed variable that specifies the new system affinity of the current thread. 


## -returns


None



## -remarks


The implementation of <b>KeSetSystemAffinityThread</b> in Windows 7 and later versions of Windows provides compatibility for drivers that were written for earlier versions of Windows, which do not support processor groups. In this implementation, <b>KeSetSystemAffinityThread</b> assigns the thread to group 0, and uses the affinity mask to specify a set of logical processors in this group on which the thread can run.

If <b>KeSetSystemAffinityThread</b> is called at IRQL &lt;= APC_LEVEL and the call is successful, the new affinity mask takes effect immediately. When the call returns, the calling thread is already running on a processor that is specified in the new affinity mask. If <b>KeSetSystemAffinityThread</b> is called at IRQL = DISPATCH_LEVEL and the call is successful, the pending processor change is deferred until the caller lowers the IRQL below DISPATCH_LEVEL.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>

<a href="..\wdm\nf-wdm-kesetsystemaffinitythreadex.md">KeSetSystemAffinityThreadEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeSetSystemAffinityThread routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

