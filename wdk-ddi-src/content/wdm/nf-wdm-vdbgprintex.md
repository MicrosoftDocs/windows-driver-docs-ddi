---
UID: NF:wdm.vDbgPrintEx
title: vDbgPrintEx function (wdm.h)
description: The vDbgPrintEx routine sends a string to the kernel debugger if certain conditions are met.
old-location: devtest\vdbgprintex.htm
tech.root: devtest
ms.assetid: e7118f5b-819f-428f-a5e6-80a36705d626
ms.date: 02/23/2018
ms.keywords: DebugFns_e3774486-d60a-4853-8d86-5ffb99ef4bcb.xml, devtest.vdbgprintex, vDbgPrintEx, vDbgPrintEx routine [Driver Development Tools], wdm/vDbgPrintEx
ms.topic: function
req.header: wdm.h
req.include-header: Dpfilter.h, Wdm.h, Ntddk.h, Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating system versions.
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
req.lib: NtDll.lib (user mode); NtosKrnl.lib (kernel mode)
req.dll: NtDll.dll (user mode); NtosKrnl.exe (kernel mode)
req.irql: "<= DIRQL (see Comments section)"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtDll.dll
- NtosKrnl.exe
api_name:
- vDbgPrintEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# vDbgPrintEx function


## -description


The <b>vDbgPrintEx</b> routine sends a string to the kernel debugger if certain conditions are met.


## -parameters




### -param ComponentId [in]

The component that is calling this routine. This parameter must be one of the component name filter IDs that are defined in Dpfilter.h. To avoid mixing your driver's output with the output of Windows components, you should use only the following values for <i>ComponentId</i>:

<ul>
<li>
DPFLTR_IHVVIDEO_ID 

</li>
<li>
DPFLTR_IHVAUDIO_ID 

</li>
<li>
DPFLTR_IHVNETWORK_ID 

</li>
<li>
DPFLTR_IHVSTREAMING_ID 

</li>
<li>
DPFLTR_IHVBUS_ID 

</li>
<li>
DPFLTR_IHVDRIVER_ID 

</li>
</ul>

### -param Level [in]

The severity of the message that is being sent. This parameter can be any 32-bit integer. Values between 0 and 31 (inclusive) are treated differently than values between 32 and 0xFFFFFFFF. For more information about how the values are treated, see <a href="https://msdn.microsoft.com/2ad320f6-596d-4b4c-bfad-d570c856bcc7">Reading and Filtering Debugging Messages</a>.


### -param Format [in]

A pointer to the format string to print. The <i>Format</i> string supports most of the <b>printf</b>-style formatting codes. However, you can use the Unicode format codes (<b>%C</b>, <b>%S</b>, <b>%lc</b>, <b>%ls</b>, <b>%wc</b>, <b>%ws</b>, and <b>%wZ</b>) only with IRQL = PASSIVE_LEVEL. The <b>vDbgPrintEx</b> routine does not support any of the floating point types (<b>%f</b>, <b>%e</b>, <b>%E</b>, <b>%g</b>, <b>%G</b>, <b>%a</b>, or <b>%A</b>).


### -param arglist [in]

An argument list for the format string. The <b>vDbgPrintEx</b> routine uses this list in the same way that <b>vprintf</b> does.


## -returns



<b>vDbgPrintEx</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine returns the appropriate error code.




## -remarks



Only kernel-mode drivers can call the <b>vDbgPrintEx</b> routine.

<b>vDbgPrintEx</b> can be called at IRQL &lt;= DIRQL. However, you can use Unicode format codes (%<b>wc</b> and %<b>ws</b>) only at IRQL = PASSIVE_LEVEL. Also, because the debugger uses interprocess interrupts (IPIs) to communicate with other processors, calling <b>vDbgPrintEx</b> at IRQL &gt; DIRQL can cause deadlocks.

<b>vDbgPrintEx</b> either passes the string that it creates to the kernel debugger or does nothing at all, depending on the values of <i>ComponentId</i>, <i>Level</i>, and the corresponding component filter masks. For more information about what <b>vDbgPrintEx</b> does, see <a href="https://msdn.microsoft.com/2ad320f6-596d-4b4c-bfad-d570c856bcc7">Reading and Filtering Debugging Messages</a>.

Unless it is absolutely necessary, you should not obtain a string from user input or another process and pass it to <b>vDbgPrintEx</b>. If you do use a string that you did not create, you must verify that this string is a valid format string and that the format codes match the argument list in type and quantity. The best coding practice is for all <i>Format</i> strings to be static and defined at compile time.

There is no upper limit to the size of the <i>Format</i> string or the number of arguments in the <i>arglist</i> list. However, any single call to <b>vDbgPrintEx</b> will transmit only 512 bytes of information. 

There is also a limit to the size of the buffer that the debugger uses. For more information about this limit, see <a href="https://msdn.microsoft.com/2ad320f6-596d-4b4c-bfad-d570c856bcc7">The DbgPrint Buffer and the Debugger</a>.

This routine is defined in Wdm.h. Component filter IDs are defined in Dpfilter.h.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543634">DbgPrintEx</a>
 

 

