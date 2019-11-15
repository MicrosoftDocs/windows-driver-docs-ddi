---
UID: NF:ntddk.KeBugCheck
title: KeBugCheck function (ntddk.h)
description: The KeBugCheck routine brings down the system in a controlled manner when the caller discovers an unrecoverable inconsistency that would corrupt the system if the caller continued to run.
old-location: kernel\kebugcheck.htm
tech.root: kernel
ms.assetid: 46337a5f-dc8a-42bc-a618-0d1440270f91
ms.date: 04/30/2018
ms.keywords: KeBugCheck, KeBugCheck routine [Kernel-Mode Driver Architecture], k105_0d6fece0-a301-44af-92b4-0ff735195c2b.xml, kernel.kebugcheck, ntddk/KeBugCheck
ms.topic: function
f1_keywords:
 - "ntddk/KeBugCheck"
req.header: ntddk.h
req.include-header: Ntddk.h
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
- KeBugCheck
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeBugCheck function


## -description


The <b>KeBugCheck</b> routine brings down the system in a controlled manner when the caller discovers an unrecoverable inconsistency that would corrupt the system if the caller continued to run. 


## -parameters




### -param BugCheckCode [in]

Specifies a value that indicates the reason for the bug check. 


## -remarks



A bug check is a system-detected error that causes an immediate, controlled shutdown of the system. Various kernel-mode components perform run-time consistency checking. When such a component discovers an unrecoverable inconsistency, it causes a bug check to be generated.

Whenever possible, all kernel-mode components should log an error and continue to run, rather than calling <b>KeBugCheck</b>. For example, if a driver is unable to allocate required resources, it should log an error so that the system continues to run; it must not generate a bug check.

A driver or other kernel-mode component should call this routine only in cases of a fatal, unrecoverable error that could corrupt the system itself.

<b>KeBugCheck</b> can be useful in the early stages of developing a driver, or while it is undergoing testing. In these circumstances, the <i>BugCheckCode</i> passed to this routine should be distinct from those codes already in use by Windows or its drivers. For a list of these codes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-code-reference2">Bug Check Codes</a>.

However, even during driver development, this routine is of only limited utility, since it results in a complete system shutdown. A more effective debugging method is to attach a kernel debugger to the system and then use routines that send messages to the debugger or break into the debugger. For further information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/using-debugging-code-in-a-driver">Using Debugging Code in a Driver</a>.

When a bug check is unavoidable, most system components call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kebugcheckex">KeBugCheckEx</a>, which provides more information about the cause of such an inconsistency than <b>KeBugCheck</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateerrorlogentry">IoAllocateErrorLogEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iowriteerrorlogentry">IoWriteErrorLogEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kebugcheckex">KeBugCheckEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterbugcheckcallback">KeRegisterBugCheckCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterbugcheckreasoncallback">KeRegisterBugCheckReasonCallback</a>
 

 

