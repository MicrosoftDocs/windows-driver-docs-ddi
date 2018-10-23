---
UID: NF:wdm.KeRegisterBugCheckReasonCallback
title: KeRegisterBugCheckReasonCallback function
author: windows-driver-content
description: The KeRegisterBugCheckReasonCallback routine registers a BugCheckDumpIoCallback, BugCheckSecondaryDumpDataCallback, or BugCheckAddPagesCallback routine, which executes when the operating system issues a bug check.
old-location: kernel\keregisterbugcheckreasoncallback.htm
tech.root: kernel
ms.assetid: 01528aa0-c580-4527-a64d-83f4ed39a471
ms.date: 04/30/2018
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeRegisterBugCheckReasonCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeRegisterBugCheckReasonCallback function


## -description


The <b>KeRegisterBugCheckReasonCallback</b> routine registers a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff540669">BugCheckAddPagesCallback</a> routine, which executes when the operating system issues a bug check.


## -parameters




### -param CallbackRecord [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551873">KBUGCHECK_REASON_CALLBACK_RECORD</a> structure that was initialized by a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552109">KeInitializeCallbackRecord</a> routine. 


### -param CallbackRoutine [in]

A pointer to the callback routine to register. This parameter points to one of the following types of driver-implemented routine: 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540669">BugCheckAddPagesCallback</a>



### -param Reason [in]

Specifies the type of callback routine that <i>CallbackRoutine</i> points to. Set <i>Reason</i> to one of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551847">KBUGCHECK_CALLBACK_REASON</a> enumeration values in the following table.

<table>
<tr>
<th>Value</th>
<th>Callback routine</th>
</tr>
<tr>
<td>
<b>KbCallbackDumpIo</b>

</td>
<td>
<i>BugCheckDumpIoCallback</i>

</td>
</tr>
<tr>
<td>
<b>KbCallbackSecondaryDumpData</b>

</td>
<td>
<i>BugCheckSecondaryDumpDataCallback</i>

</td>
</tr>
<tr>
<td>
<b>KbCallbackAddPages</b>

</td>
<td>
<i>BugCheckAddPagesCallback</i>

</td>
</tr>
</table>
 


### -param Component [in]

A pointer to a null-terminated ANSI string that identifies the caller. For example, you can select a string that describes the device driver, or that contains the device name. You can use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562171">!bugdump</a> debugger extension to display the crash dump data that is associated with this string.


## -returns



<b>KeRegisterBugCheckReasonCallback</b> returns <b>TRUE</b> if the callback routine is successfully registered; otherwise, it returns <b>FALSE</b>.




## -remarks



Drivers can use <b>KeRegisterBugCheckReasonCallback</b> to register routines that execute during a system bug check.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a> routines are called each time data is written to the crash dump file. Drivers for devices that monitor the system state can register a <i>BugCheckDumpIoCallback</i> routine to copy the crash dump data to the monitoring device.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a> routines are called to poll drivers for any device-specific information that should be added to the secondary data area of a crash dump file.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff540669">BugCheckAddPagesCallback</a> routines are called to enable drivers to add pages of driver-specific data to the primary data area of a crash dump file. <i>BugCheckAddPagesCallback</i> routines are supported in Windows Server 2008 and later versions of Windows.

Drivers can use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552003">KeDeregisterBugCheckReasonCallback</a> routine to remove the <i>BugCheckXxxCallback</i> registration. Any driver that can be unloaded must remove the registrations of all of its callbacks in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a> routine.

To display secondary dump data, you can use the <a href="https://go.microsoft.com/fwlink/p/?linkid=165501">.enumtag</a> command or the <a href="https://go.microsoft.com/fwlink/p/?linkid=165500">IDebugDataSpaces3::ReadTagged</a> method in a debugger extension. Another option is to debug the bug check callback routine itself. For more information about debuggers and debugger extensions, see <a href="https://msdn.microsoft.com/938ef180-84de-442f-9b6c-1138c2fc8d5a">Windows Debugging</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540669">BugCheckAddPagesCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540674">BugCheckCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540677">BugCheckDumpIoCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540679">BugCheckSecondaryDumpDataCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551847">KBUGCHECK_CALLBACK_REASON</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551873">KBUGCHECK_REASON_CALLBACK_RECORD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552003">KeDeregisterBugCheckReasonCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552109">KeInitializeCallbackRecord</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553105">KeRegisterBugCheckCallback</a>
 

 

