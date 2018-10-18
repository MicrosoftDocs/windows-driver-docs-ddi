---
UID: NF:wdm.vDbgPrintExWithPrefix
title: vDbgPrintExWithPrefix function
author: windows-driver-content
description: The vDbgPrintExWithPrefix routine sends a string to the kernel debugger if certain conditions that you specify are met. This routine can append a prefix to debugger output to help organize debugging results.
old-location: devtest\vdbgprintexwithprefix.htm
tech.root: devtest
ms.assetid: bd7acc4e-9941-45a1-ad90-996e80c1937b
ms.date: 2/23/2018
ms.keywords: DebugFns_483dc845-dd53-48a5-b879-cf69158016aa.xml, devtest.vdbgprintexwithprefix, vDbgPrintExWithPrefix, vDbgPrintExWithPrefix routine [Driver Development Tools], wdm/vDbgPrintExWithPrefix
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtDll.dll
-	NtosKrnl.exe
api_name:
-	vDbgPrintExWithPrefix
product:
- Windows
targetos: Windows
req.typenames: 
---

# vDbgPrintExWithPrefix function


## -description


The <b>vDbgPrintExWithPrefix</b> routine sends a string to the kernel debugger if certain conditions that you specify are met. This routine can append a prefix to debugger output to help organize debugging results.


## -parameters




### -param Prefix [in]

A string that is appended at the start of debugger output. You can use this string to organize debugger output by adding a unique identifier.

For example, a component-specific routine could specify the component's name when it calls <b>vDbgPrintExWithPrefix</b>. This routine would automatically add the component name to the beginning of all debug output that is passed to the component's debug print routine.


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

A pointer to the format string to print. The <i>Format</i> string supports most of the <b>printf</b>-style formatting codes. However, you can use the Unicode format codes (<b>%C</b>, <b>%S</b>, <b>%lc</b>, <b>%ls</b>, <b>%wc</b>, <b>%ws</b>, and <b>%wZ</b>) only with IRQL = PASSIVE_LEVEL. The <b>vDbgPrintExWithPrefix</b> routine does not support any of the floating point types (<b>%f</b>, <b>%e</b>, <b>%E</b>, <b>%g</b>, <b>%G</b>, <b>%a</b>, or <b>%A</b>).


### -param arglist [in]

An argument list for the format string. The <b>vDbgPrintExWithPrefix</b> routine uses this list in the same way that <b>vprintf</b> does.


## -returns



<b>vDbgPrintExWithPrefix</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine returns the appropriate error code.




## -remarks



Only kernel-mode drivers can call the <b>vDbgPrintExWithPrefix</b> routine.

<b>vDbgPrintExWithPrefix</b> can be called at IRQL &lt;= DIRQL. However, you can use Unicode format codes (<b>%wc</b> and <b>%ws</b>) only at IRQL = PASSIVE_LEVEL. Also, because the debugger uses interprocess interrupts (IPIs) to communicate with other processors, a call to <b>vDbgPrintExWithPrefix</b> at IRQL &gt; DIRQL can cause deadlocks.

<b>vDbgPrintExWithPrefix</b> either passes the string that it creates to the kernel debugger or does nothing at all, depending on the values of <i>ComponentId</i>, <i>Level</i>, and the corresponding component filter masks. For more information about what <i>vDbgPrintEx</i> does, see <a href="https://msdn.microsoft.com/2ad320f6-596d-4b4c-bfad-d570c856bcc7">Reading and Filtering Debugging Messages</a>.

Unless it is absolutely necessary, you should not obtain a string from user input or another process and pass it to <b>vDbgPrintExWithPrefix</b>. If you do use a string that you did not create, you must verify that this string is a valid format string and that the format codes match the argument list in type and quantity. The best coding practice is for all <i>Format</i> strings to be static and defined at compile time.

There is no upper limit to the size of the <i>Format</i> string or the number of arguments in the <i>arglist</i> list. However, any single call to <b>vDbgPrintExWithPrefix</b> transmits only 512 bytes of information. 

There is also a limit to the size of the buffer that the debugger uses. For more information about this limit, see <a href="https://msdn.microsoft.com/2ad320f6-596d-4b4c-bfad-d570c856bcc7">The DbgPrint Buffer and the Debugger</a>.

This routine is defined in Wdm.h. Component filter IDs are defined in Dpfilter.h.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543634">DbgPrintEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556075">vDbgPrintEx</a>
 

 

