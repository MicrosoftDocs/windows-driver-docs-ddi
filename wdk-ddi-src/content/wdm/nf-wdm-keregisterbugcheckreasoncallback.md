---
UID: NF:wdm.KeRegisterBugCheckReasonCallback
title: KeRegisterBugCheckReasonCallback function (wdm.h)
description: The KeRegisterBugCheckReasonCallback routine registers a KbCallbackDumpIo, KbCallbackSecondaryDumpData, or KbCallbackAddPages routine, which executes when the operating system issues a bug check.
old-location: kernel\keregisterbugcheckreasoncallback.htm
tech.root: kernel
ms.assetid: 01528aa0-c580-4527-a64d-83f4ed39a471
ms.date: 05/03/2018
keywords: ["KeRegisterBugCheckReasonCallback function"]
ms.keywords: KeRegisterBugCheckReasonCallback, KeRegisterBugCheckReasonCallback routine [Kernel-Mode Driver Architecture], k105_6b2fbc25-072d-470f-9860-e820e60cdf90.xml, kernel.keregisterbugcheckreasoncallback, wdm/KeRegisterBugCheckReasonCallback
f1_keywords:
 - "wdm/KeRegisterBugCheckReasonCallback"
 - "KeRegisterBugCheckReasonCallback"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP Service Pack 1 (SP1), Windows Server 2003, and later versions of Windows.
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
- KeRegisterBugCheckReasonCallback
targetos: Windows
req.typenames: 
---

# KeRegisterBugCheckReasonCallback function

## -description

The <b>KeRegisterBugCheckReasonCallback</b> function registers a callback routine that executes when the operating system issues a bug check.

## -parameters

### -param CallbackRecord 
[out]
A pointer to a <b><a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KBUGCHECK_REASON_CALLBACK_RECORD</a></b> structure that was initialized by a call to the <b><a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">KeInitializeCallbackRecord</a></b> routine. 


### -param CallbackRoutine 
[in]
A pointer to a callback routine of type [*KBUGCHECK_REASON_CALLBACK_ROUTINE*](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kbugcheck_reason_callback_routine) to register. For information about how to implement this callback routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

### -param Reason 
[in]
An enumeration of type <b><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_kbugcheck_callback_reason">KBUGCHECK_CALLBACK_REASON</a></b> that specifies the type of callback routine that <i>CallbackRoutine</i> points to.

### -param Component 
[in]
A pointer to a null-terminated ANSI string that identifies the caller. For example, you can select a string that describes the device driver, or that contains the device name. You can use the <b><a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-bugdump">!bugdump</a></b> debugger extension to display the crash dump data that is associated with this string.

## -returns

<b>KeRegisterBugCheckReasonCallback</b> returns <b>TRUE</b> if the callback routine is successfully registered; otherwise, it returns <b>FALSE</b>.

## -remarks

Drivers can use <b>KeRegisterBugCheckReasonCallback</b> to register routines that execute during a system bug check.

For descriptions of each type of callback, see [**KBUGCHECK_CALLBACK_REASON**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_kbugcheck_callback_reason).

Drivers can use the [**KeDeregisterBugCheckReasonCallback**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kederegisterbugcheckcallback) routine to remove the bug check callback registration. Any driver that can be unloaded must remove the registrations of all of its callbacks in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload">Unload</a> routine.

For information about how to implement these callback routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

To display secondary dump data, you can use the <b><a href="https://go.microsoft.com/fwlink/p/?linkid=165501">.enumtag</a></b> command or the <b><a href="https://go.microsoft.com/fwlink/p/?linkid=165500">IDebugDataSpaces3::ReadTagged</a></b> method in a debugger extension. Another option is to debug the bug check callback routine itself. For more information about debuggers and debugger extensions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/index">Windows Debugging</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

<b><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_kbugcheck_callback_reason">KBUGCHECK_CALLBACK_REASON</a></b>

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KBUGCHECK_REASON_CALLBACK_RECORD</a>

<b><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kederegisterbugcheckreasoncallback">KeDeregisterBugCheckReasonCallback</a></b>

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">KeInitializeCallbackRecord</a>

<b><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterbugcheckcallback">KeRegisterBugCheckCallback</a></b>
