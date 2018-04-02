---
UID: NF:wdm.KeBugCheckEx
title: KeBugCheckEx function
author: windows-driver-content
description: The KeBugCheckEx routine brings down the system in a controlled manner when the caller discovers an unrecoverable inconsistency that would corrupt the system if the caller continued to run.
old-location: kernel\kebugcheckex.htm
old-project: kernel
ms.assetid: 2330fda2-71f5-4a8b-8124-775a40926bc1
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeBugCheckEx, KeBugCheckEx routine [Kernel-Mode Driver Architecture], k105_17af10bb-b21d-408e-bf73-421ce705d117.xml, kernel.kebugcheckex, wdm/KeBugCheckEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
-	KeBugCheckEx
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeBugCheckEx function


## -description


The <b>KeBugCheckEx</b> routine brings down the system in a controlled manner when the caller discovers an unrecoverable inconsistency that would corrupt the system if the caller continued to run.


## -parameters




### -param BugCheckCode [in]

Specifies a value that indicates the reason for the bug check.


### -param BugCheckParameter1 [in]


### -param BugCheckParameter2 [in]


### -param BugCheckParameter3 [in]


### -param BugCheckParameter4 [in]

The four <i>BugCheckParameterX</i> values supply additional information, such as the address and data where a memory-corruption error occurred, depending on the value of <i>BugCheckCode</i>.


## -returns



None




## -remarks



A bug check is a system-detected error that causes an immediate, controlled shutdown of the system. Various kernel-mode components perform run-time consistency checking. When such a component discovers an unrecoverable inconsistency, it causes a bug check to be generated.

Whenever possible, all kernel-mode components should log an error and continue to run, rather than calling <b>KeBugCheckEx</b>. For example, if a driver is unable to allocate required resources, it should log an error so that the system continues to run; it must not generate a bug check.

A driver or other kernel-mode component should call this routine only in cases of a fatal, unrecoverable error that could corrupt the system itself.

<b>KeBugCheckEx</b> can be useful in the early stages of developing a driver, or while it is undergoing testing. In these circumstances, the <i>BugCheckCode</i> passed to this routine should be distinct from those codes already in use by Windows or its drivers. For a list of these codes, see <a href="https://msdn.microsoft.com/DBA85578-97CF-4BD7-A67D-1C7AD2E9B2BB">Bug Check Codes</a>.

However, even during driver development, this routine is of only limited utility, since it results in a complete system shutdown. A more effective debugging method is to attach a kernel debugger to the system and then use routines that send messages to the debugger or break into the debugger. For further information, see <a href="https://msdn.microsoft.com/6ed74bcc-290c-44e3-943e-4169527dfa18">Using Debugging Code in a Driver</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548245">IoAllocateErrorLogEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550527">IoWriteErrorLogEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551948">KeBugCheck</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553105">KeRegisterBugCheckCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553110">KeRegisterBugCheckReasonCallback</a>
 

 

