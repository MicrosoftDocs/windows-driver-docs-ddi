---
UID: NF:wdm.KeRegisterBugCheckReasonCallback
title: KeRegisterBugCheckReasonCallback function (wdm.h)
description: The KeRegisterBugCheckReasonCallback routine registers a KbCallbackDumpIo, KbCallbackSecondaryDumpData, or KbCallbackAddPages routine, which executes when the operating system issues a bug check.
old-location: kernel\keregisterbugcheckreasoncallback.htm
tech.root: kernel
ms.date: 05/27/2021
keywords: ["KeRegisterBugCheckReasonCallback function"]
ms.keywords: KeRegisterBugCheckReasonCallback, KeRegisterBugCheckReasonCallback routine [Kernel-Mode Driver Architecture], k105_6b2fbc25-072d-470f-9860-e820e60cdf90.xml, kernel.keregisterbugcheckreasoncallback, wdm/KeRegisterBugCheckReasonCallback
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KeRegisterBugCheckReasonCallback
 - wdm/KeRegisterBugCheckReasonCallback
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeRegisterBugCheckReasonCallback
---

# KeRegisterBugCheckReasonCallback function

## -description

The **KeRegisterBugCheckReasonCallback** function registers a callback routine that executes when the operating system issues a bug check.

## -parameters

### -param CallbackRecord [out]


A pointer to a [**KBUGCHECK_REASON_CALLBACK_RECORD**](./ns-wdm-_kbugcheck_reason_callback_record.md) structure that was initialized by a call to the KeInitializeCallbackRecord routine described in the [Windows kernel macros](/windows-hardware/drivers/kernel/mm-bad-pointer).

### -param CallbackRoutine [in]


A pointer to a callback routine of type [**KBUGCHECK_REASON_CALLBACK_ROUTINE**](./nc-wdm-kbugcheck_reason_callback_routine.md) to register. For information about how to implement this callback routine, see [Writing a Bug Check Callback Routine](/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine).

### -param Reason [in]


An enumeration of type [**KBUGCHECK_CALLBACK_REASON**](./ne-wdm-_kbugcheck_callback_reason.md) that specifies the type of callback routine that *CallbackRoutine* points to.

### -param Component [in]


A pointer to a null-terminated ANSI string that identifies the caller. For example, you can select a string that describes the device driver, or that contains the device name. You can use the [!bugdump](/windows-hardware/drivers/debugger/-bugdump) debugger extension to display the crash dump data that is associated with this string.

## -returns

**KeRegisterBugCheckReasonCallback** returns **TRUE** if the callback routine is successfully registered; otherwise, it returns **FALSE**.

## -remarks

Drivers can use **KeRegisterBugCheckReasonCallback** to register routines that execute during a system bug check.

For descriptions of each type of callback, see [**KBUGCHECK_CALLBACK_REASON**](./ne-wdm-_kbugcheck_callback_reason.md).

Drivers can use the [**KeDeregisterBugCheckReasonCallback**](./nf-wdm-kederegisterbugcheckreasoncallback.md) routine to remove the bug check callback registration. Any driver that can be unloaded must remove the registrations of all of its callbacks in its [Unload](./nc-wdm-driver_unload.md) routine.

For information about how to implement these callback routines, see [Writing a Bug Check Callback Routine](/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine).

To display secondary dump data, you can use the [IDebugDataSpaces3::ReadTagged](../dbgeng/nf-dbgeng-idebugdataspaces3-readtagged.md)** method in a debugger extension. Another option is to debug the bug check callback routine itself. For more information about debuggers and debugger extensions, see [Windows Debugging](/windows-hardware/drivers/debugger/index).

## -see-also

[Writing a Bug Check Callback Routine](/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine)

[**KBUGCHECK_CALLBACK_REASON**](./ne-wdm-_kbugcheck_callback_reason.md)

[**KBUGCHECK_REASON_CALLBACK_RECORD**](/windows-hardware/drivers/kernel/eprocess)

[**KeDeregisterBugCheckReasonCallback**](./nf-wdm-kederegisterbugcheckreasoncallback.md)

[**KeInitializeCallbackRecord**](/windows-hardware/drivers/kernel/mm-bad-pointer)

[**KeRegisterBugCheckCallback**](./nf-wdm-keregisterbugcheckcallback.md)
