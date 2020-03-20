---
UID: NF:wdm.KeBugCheckEx
title: KeBugCheckEx function (wdm.h)
description: The KeBugCheckEx routine brings down the system in a controlled manner when the caller discovers an unrecoverable inconsistency that would corrupt the system if the caller continued to run.
old-location: kernel\kebugcheckex.htm
tech.root: kernel
ms.assetid: 2330fda2-71f5-4a8b-8124-775a40926bc1
ms.date: 04/30/2018
keywords: ["KeBugCheckEx function"]
ms.keywords: KeBugCheckEx, KeBugCheckEx routine [Kernel-Mode Driver Architecture], k105_17af10bb-b21d-408e-bf73-421ce705d117.xml, kernel.kebugcheckex, wdm/KeBugCheckEx
f1_keywords:
 - "wdm/KeBugCheckEx"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeBugCheckEx
product:
- Windows
targetos: Windows
req.typenames: 
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


## -remarks



A bug check is a system-detected error that causes an immediate, controlled shutdown of the system. Various kernel-mode components perform run-time consistency checking. When such a component discovers an unrecoverable inconsistency, it causes a bug check to be generated.

Whenever possible, all kernel-mode components should log an error and continue to run, rather than calling <b>KeBugCheckEx</b>. For example, if a driver is unable to allocate required resources, it should log an error so that the system continues to run; it must not generate a bug check.

A driver or other kernel-mode component should call this routine only in cases of a fatal, unrecoverable error that could corrupt the system itself.

<b>KeBugCheckEx</b> can be useful in the early stages of developing a driver, or while it is undergoing testing. In these circumstances, the <i>BugCheckCode</i> passed to this routine should be distinct from those codes already in use by Windows or its drivers. For a list of these codes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-code-reference2">Bug Check Codes</a>.

However, even during driver development, this routine is of only limited utility, since it results in a complete system shutdown. A more effective debugging method is to attach a kernel debugger to the system and then use routines that send messages to the debugger or break into the debugger. For further information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/using-debugging-code-in-a-driver">Using Debugging Code in a Driver</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateerrorlogentry">IoAllocateErrorLogEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iowriteerrorlogentry">IoWriteErrorLogEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kebugcheck">KeBugCheck</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterbugcheckcallback">KeRegisterBugCheckCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterbugcheckreasoncallback">KeRegisterBugCheckReasonCallback</a>
 

 

