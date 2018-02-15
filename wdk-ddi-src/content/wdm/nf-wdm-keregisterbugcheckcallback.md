---
UID: NF:wdm.KeRegisterBugCheckCallback
title: KeRegisterBugCheckCallback function
author: windows-driver-content
description: The KeRegisterBugCheckCallback routine registers a BugCheckCallback routine, which executes when the operating system issues a bug check.
old-location: kernel\keregisterbugcheckcallback.htm
old-project: kernel
ms.assetid: 6a4ab5a4-4d09-4fd5-bc7b-0a8e5a634eb3
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/KeRegisterBugCheckCallback, KeRegisterBugCheckCallback routine [Kernel-Mode Driver Architecture], kernel.keregisterbugcheckcallback, KeRegisterBugCheckCallback, k105_42736e68-1f5a-47df-976a-df3bfa9a356e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeRegisterBugCheckCallback
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeRegisterBugCheckCallback function


## -description


The <b>KeRegisterBugCheckCallback</b> routine registers a <a href="..\wdm\nc-wdm-kbugcheck_callback_routine.md">BugCheckCallback</a> routine, which executes when the operating system issues a bug check.


## -syntax


````
BOOLEAN KeRegisterBugCheckCallback(
  _Out_    PKBUGCHECK_CALLBACK_RECORD  CallbackRecord,
  _In_     PKBUGCHECK_CALLBACK_ROUTINE CallbackRoutine,
  _In_opt_ PVOID                       Buffer,
  _In_     ULONG                       Length,
  _In_     PUCHAR                      Component
);
````


## -parameters




### -param CallbackRecord [out]

Pointer to a callback record that was previously initialized by <a href="https://msdn.microsoft.com/library/windows/hardware/ff552109">KeInitializeCallbackRecord</a>, for which the caller provides nonpaged storage. 


### -param CallbackRoutine [in]

Pointer to the driver-supplied <a href="..\wdm\nc-wdm-kbugcheck_callback_routine.md">BugCheckCallback</a> routine. 


### -param Buffer [in, optional]

Pointer to a caller-supplied buffer, which must be in resident memory, such as nonpaged pool. 


### -param Length [in]

Specifies the size in bytes of the caller-allocated buffer. 


### -param Component [in]

Pointer to a null-terminated ANSI string that identifies the caller. This string usually contains the name of the device driver, or possibly of its device. 


## -returns



<b>KeRegisterBugCheckCallback</b> returns <b>TRUE</b> if the caller-supplied routine is successfully added to the set of registered bug-check callbacks; otherwise, it returns <b>FALSE</b>. 




## -remarks



The <b>KeRegisterBugCheckCallback</b> routine registers a <a href="..\wdm\nc-wdm-kbugcheck_callback_routine.md">BugCheckCallback</a> routine, the simplest kind of bug-check callback routine. To register other kinds of bug-check callbacks, such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a> and <a href="..\wdm\nc-wdm-kbugcheck_reason_callback_routine.md">BugCheckAddPagesCallback</a> routines, use the <a href="..\wdm\nf-wdm-keregisterbugcheckreasoncallback.md">KeRegisterBugCheckReasonCallback</a> routine instead.

The <i>BugCheckCallback</i> routine is executed when the system issues a bug check. A driver can use the routine to reset the device to a known state. For more information, see <i>BugCheckCallback</i>.

Drivers can use the <b>KeDeregisterBugCheckCallback</b> routine to remove the callback. Any driver that can be unloaded must remove all of its callbacks in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a> routine.

The <i>Component</i> string is used to identify the driver during crash-dump debugging. To display the crash dump data corresponding to any specified <i>Component</i> string, you can use the <b>!bugdump</b> debugger extension. It is also possible to debug the bug check callback routine itself. For information about debuggers and debugger extensions, see <a href="https://msdn.microsoft.com/938ef180-84de-442f-9b6c-1138c2fc8d5a">Windows Debugging</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552109">KeInitializeCallbackRecord</a>



<a href="..\wdm\nf-wdm-kederegisterbugcheckcallback.md">KeDeregisterBugCheckCallback</a>



<a href="..\wdm\nc-wdm-kbugcheck_reason_callback_routine.md">BugCheckAddPagesCallback</a>



<a href="..\wdm\nf-wdm-keregisterbugcheckreasoncallback.md">KeRegisterBugCheckReasonCallback</a>



<a href="..\wdm\nc-wdm-kbugcheck_callback_routine.md">BugCheckCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeRegisterBugCheckCallback routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

