---
UID: NF:wdm.KeBugCheckEx
title: KeBugCheckEx function
author: windows-driver-content
description: The KeBugCheckEx routine brings down the system in a controlled manner when the caller discovers an unrecoverable inconsistency that would corrupt the system if the caller continued to run.
old-location: kernel\kebugcheckex.htm
old-project: kernel
ms.assetid: 2330fda2-71f5-4a8b-8124-775a40926bc1
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeBugCheckEx
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
req.alt-api: KeBugCheckEx
req.alt-loc: NtosKrnl.exe
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeBugCheckEx function



## -description
The <b>KeBugCheckEx</b> routine brings down the system in a controlled manner when the caller discovers an unrecoverable inconsistency that would corrupt the system if the caller continued to run.



## -syntax

````
VOID  KeBugCheckEx(
  _In_ ULONG     BugCheckCode,
  _In_ ULONG_PTR BugCheckParameter1,
  _In_ ULONG_PTR BugCheckParameter2,
  _In_ ULONG_PTR BugCheckParameter3,
  _In_ ULONG_PTR BugCheckParameter4
);
````


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
<dl>
<dt>
<a href="..\wdm\nf-wdm-ioallocateerrorlogentry.md">IoAllocateErrorLogEntry</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-iowriteerrorlogentry.md">IoWriteErrorLogEntry</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-kebugcheck.md">KeBugCheck</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keregisterbugcheckcallback.md">KeRegisterBugCheckCallback</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keregisterbugcheckreasoncallback.md">KeRegisterBugCheckReasonCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeBugCheckEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

