---
UID: NF:wdm.KeRegisterBugCheckReasonCallback
title: KeRegisterBugCheckReasonCallback function (wdm.h)
description: The KeRegisterBugCheckReasonCallback routine registers a KbCallbackDumpIo, KbCallbackSecondaryDumpData, or KbCallbackAddPages routine, which executes when the operating system issues a bug check.
old-location: kernel\keregisterbugcheckreasoncallback.htm
tech.root: kernel
ms.assetid: 01528aa0-c580-4527-a64d-83f4ed39a471
ms.date: 05/03/2018
ms.keywords: KeRegisterBugCheckReasonCallback, KeRegisterBugCheckReasonCallback routine [Kernel-Mode Driver Architecture], k105_6b2fbc25-072d-470f-9860-e820e60cdf90.xml, kernel.keregisterbugcheckreasoncallback, wdm/KeRegisterBugCheckReasonCallback
ms.topic: function
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeRegisterBugCheckReasonCallback function

## -description

The <b>KeRegisterBugCheckReasonCallback</b> function registers one of the callback routines defined in defined in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_kbugcheck_callback_reason">KBUGCHECK_CALLBACK_REASON</a> enumeration, which executes when the operating system issues a bug check.

## -parameters

### -param CallbackRecord [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551873">KBUGCHECK_REASON_CALLBACK_RECORD</a> structure that was initialized by a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552109">KeInitializeCallbackRecord</a> routine. 


### -param CallbackRoutine [in]

A pointer to the callback routine to register. This parameter points to one of the types of driver-implemented routine defined in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551847">KBUGCHECK_CALLBACK_REASON</a> enumeration. For information about how to implement this callback routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

### -param Reason [in]

Specifies the type of callback routine that <i>CallbackRoutine</i> points to. Set <i>Reason</i> to one of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551847">KBUGCHECK_CALLBACK_REASON</a> enumeration values in the following table.

<table>
<tr>
<th>Value</th>
<th>Data Structure</th>
</tr>

<tr>
<td>
<b>KbCallbackAddPages</b>
</td>
<td>
<b><b><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_kbugcheck_add_pages">KBUGCHECK_ADD_PAGES structure</a></b>
</b>
</td>
</tr>

<tr>
<td>
<b>KbCallbackDumpIo</b>
</td>
<td>
<b><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_kbugcheck_dump_io">KBUGCHECK_DUMP_IO structure</a></b>
</td>
</tr>

<tr>
<td>
<b>KbCallbackSecondaryDumpData</b>
<td>
<b><a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_kbugcheck_secondary_dump_data">KBUGCHECK_SECONDARY_DUMP_DATA structure</a></b>
</td>
</td>
</tr>

<tr>
<td>
<b>KbCallbackSecondaryMultiPartDumpData</b>
</td>
<td>
<b>KBUGCHECK_SECONDARY_DUMP_DATA_EX</b>
</td>
</tr>

<tr>
<td>
<b>KbCallbackRemovePages</b>
</td>
<td>
<b>KBUGCHECK_REMOVE_PAGES</b>
</td>
</tr>

<tr>
<td>
<b>KbCallbackTriageDumpData</b>
</td>
<td>
<b>KBUGCHECK_TRIAGE_DUMP_DATA</b>
</td>
</tr>

</table>

### -param Component [in]

A pointer to a null-terminated ANSI string that identifies the caller. For example, you can select a string that describes the device driver, or that contains the device name. You can use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562171">!bugdump</a> debugger extension to display the crash dump data that is associated with this string.

## -returns

<b>KeRegisterBugCheckReasonCallback</b> returns <b>TRUE</b> if the callback routine is successfully registered; otherwise, it returns <b>FALSE</b>.

## -remarks

Drivers can use <b>KeRegisterBugCheckReasonCallback</b> to register routines that execute during a system bug check.

**KbCallbackDumpIo** routines are called each time data is written to the crash dump file. Drivers for devices that monitor the system state can register a <i>KbCallbackDumpIo</i> routine to copy the crash dump data to the monitoring device.

**KbCallbackSecondaryDumpData** routines are called to poll drivers for any device-specific information that should be added to the secondary data area of a crash dump file.

**KbCallbackAddPages** routines are called to enable drivers to add pages of driver-specific data to the primary data area of a crash dump file. They are supported in Windows Server 2008 and later versions of Windows.

Drivers can use the KeDeregisterBugCheckReasonCallback routine to remove the bug check callback registration. Any driver that can be unloaded must remove the registrations of all of its callbacks in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a> routine.

For information about how to implement these callback routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

To display secondary dump data, you can use the <a href="https://go.microsoft.com/fwlink/p/?linkid=165501">.enumtag</a> command or the <a href="https://go.microsoft.com/fwlink/p/?linkid=165500">IDebugDataSpaces3::ReadTagged</a> method in a debugger extension. Another option is to debug the bug check callback routine itself. For more information about debuggers and debugger extensions, see <a href="https://msdn.microsoft.com/938ef180-84de-442f-9b6c-1138c2fc8d5a">Windows Debugging</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-a-bug-check-callback-routine">Writing a Bug Check Callback Routine</a>.

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551847">KBUGCHECK_CALLBACK_REASON</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551873">KBUGCHECK_REASON_CALLBACK_RECORD</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552003">KeDeregisterBugCheckReasonCallback</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552109">KeInitializeCallbackRecord</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553105">KeRegisterBugCheckCallback</a>
