---
UID: NF:wdm.KeRegisterBugCheckCallback
title: KeRegisterBugCheckCallback function (wdm.h)
description: The KeRegisterBugCheckCallback routine registers a BugCheckCallback routine, which executes when the operating system issues a bug check.
old-location: kernel\keregisterbugcheckcallback.htm
tech.root: kernel
ms.assetid: 6a4ab5a4-4d09-4fd5-bc7b-0a8e5a634eb3
ms.date: 04/30/2018
keywords: ["KeRegisterBugCheckCallback function"]
ms.keywords: KeRegisterBugCheckCallback, KeRegisterBugCheckCallback routine [Kernel-Mode Driver Architecture], k105_42736e68-1f5a-47df-976a-df3bfa9a356e.xml, kernel.keregisterbugcheckcallback, wdm/KeRegisterBugCheckCallback
f1_keywords:
 - "wdm/KeRegisterBugCheckCallback"
 - "KeRegisterBugCheckCallback"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeRegisterBugCheckCallback
targetos: Windows
req.typenames: 
---

# KeRegisterBugCheckCallback function

## -description

The <b>KeRegisterBugCheckCallback</b> routine registers a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kbugcheck_callback_routine">BugCheckCallback</a> routine, which executes when the operating system issues a bug check.

## -parameters

### -param CallbackRecord [out]

Pointer to a callback record that was previously initialized by <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">KeInitializeCallbackRecord</a>, for which the caller provides nonpaged storage. 

### -param CallbackRoutine [in]

Pointer to the driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kbugcheck_callback_routine">KBUGCHECK_CALLBACK_ROUTINE callback function</a>. 

### -param Buffer [in, optional]

Pointer to a caller-supplied buffer, which must be in resident memory, such as nonpaged pool. 

### -param Length [in]

Specifies the size in bytes of the caller-allocated buffer. 

### -param Component [in]

Pointer to a null-terminated ANSI string that identifies the caller. This string usually contains the name of the device driver, or possibly of its device. 

## -returns

<b>KeRegisterBugCheckCallback</b> returns <b>TRUE</b> if the caller-supplied routine is successfully added to the set of registered bug-check callbacks; otherwise, it returns <b>FALSE</b>. 

## -remarks

The <b>KeRegisterBugCheckCallback</b> routine registers a BugCheckCallback routine, the simplest kind of bug-check callback routine.

To register other kinds of bug-check callbacks, such as KbCallbackDumpIo and KbCallbackAddPages routines, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterbugcheckreasoncallback">KeRegisterBugCheckReasonCallback</a> routine instead.

The <i>BugCheckCallback</i> routine is executed when the system issues a bug check. A driver can use the routine to reset the device to a known state. For more information, see <i>BugCheckCallback</i>.

Drivers can use the <b>KeDeregisterBugCheckCallback</b> routine to remove the callback. Any driver that can be unloaded must remove all of its callbacks in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload">Unload</a> routine.

The <i>Component</i> string is used to identify the driver during crash-dump debugging. To display the crash dump data corresponding to any specified <i>Component</i> string, you can use the <b>!bugdump</b> debugger extension. It is also possible to debug the bug check callback routine itself. For information about debuggers and debugger extensions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/index">Windows Debugging</a>.

**Implementation**

To define a BugCheckCallback callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps Code Analysis for Drivers, Static Driver Verifier (SDV), and other verification tools find errors.

For example, to define a BugCheckCallback callback routine that is named MyBugCheckCallback, use the KBUGCHECK_CALLBACK_ROUTINE type as shown in this code example:

```cpp 
KBUGCHECK_CALLBACK_ROUTINE MyBugCheckCallback;
``` 

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
VOID
  MyBugCheckCallback(
    PVOID  Buffer,
    ULONG  Length
    )
  {
      // Function body
  }
```

The KBUGCHECK_CALLBACK_ROUTINE function type is defined in the Wdm.h header file.

To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_ annotation` to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the KBUGCHECK_CALLBACK_ROUTINE function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about _Use_decl_annotations_, see [Annotating Function Behavior](https://docs.microsoft.com/visualstudio/code-quality/annotating-function-behavior).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kederegisterbugcheckcallback">KeDeregisterBugCheckCallback</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">KeInitializeCallbackRecord</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterbugcheckreasoncallback">KeRegisterBugCheckReasonCallback</a>
