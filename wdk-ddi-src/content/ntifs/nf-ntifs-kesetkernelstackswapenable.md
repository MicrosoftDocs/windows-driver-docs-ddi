---
UID: NF:ntifs.KeSetKernelStackSwapEnable
title: KeSetKernelStackSwapEnable function
author: windows-driver-content
description: The KeSetKernelStackSwapEnable routine enables and disables swapping of the caller's stack to disk.
old-location: kernel\kesetkernelstackswapenable.htm
old-project: kernel
ms.assetid: ec914f67-b2c2-4370-8685-770bca045034
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k105_160eb1a2-1d12-4ca4-b83d-4bcb5636145e.xml, KeSetKernelStackSwapEnable, KeSetKernelStackSwapEnable routine [Kernel-Mode Driver Architecture], kernel.kesetkernelstackswapenable, ntifs/KeSetKernelStackSwapEnable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeSetKernelStackSwapEnable
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# KeSetKernelStackSwapEnable function


## -description


The <b>KeSetKernelStackSwapEnable</b> routine enables and disables swapping of the caller's stack to disk. 


## -syntax


````
BOOLEAN KeSetKernelStackSwapEnable(
  _In_ BOOLEAN Enable
);
````


## -parameters




#### - Enable [in]

Specifies whether to enable swapping of the stack that belongs to the calling thread. If <b>TRUE</b>, swapping is enabled and the contents of the stack can be paged in and out of memory. If <b>FALSE</b>, swapping is disabled and the stack is memory-resident. 


## -returns


<b>KeSetKernelStackSwapEnable</b> returns a BOOLEAN value that indicates whether stack swapping was enabled at the time that the call was initiated. This value is <b>TRUE</b> if stack swapping was previously enabled and is <b>FALSE</b> if it was disabled. 



## -remarks


A kernel-mode driver can call this routine to control whether its stack is pageable or locked in memory.

Stack swapping can occur only if the thread is in a wait state that was caused by a request from a user-mode application. Stack swapping never occurs for wait states that are initiated by kernel-mode components, regardless of whether stack swapping is enabled.

It is not typically necessary to disable stack swapping. Do this only in  rare cases. For an example that discusses alternatives to disabling stack swapping, see the following Examples section.

In a call to a kernel-mode wait routine, such as <a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>, the caller specifies a <i>WaitMode</i> parameter to indicate whether the caller waits in kernel mode or user mode. If <i>WaitMode</i> = <b>UserMode</b>, and if the wait duration is sufficiently long, the memory manager might page out sections of the stack that belongs to the waiting thread. However, if the stack contains data items that must remain memory-resident for the duration of the wait, the thread can prevent the stack from being paged out by calling <b>KeSetKernelStackSwapEnable</b> and specifying <i>Enable</i> = <b>FALSE</b>.

A thread must not exit (terminate) while stack swapping is disabled or a system bug check will occur.



## -see-also

<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>

<a href="..\wdm\nf-wdm-keinitializeevent.md">KeInitializeEvent</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeSetKernelStackSwapEnable routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

