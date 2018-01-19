---
UID: NF:wdm.DbgPrintEx
title: DbgPrintEx function
author: windows-driver-content
description: The DbgPrintEx routine sends a string to the kernel debugger if the conditions you specify are met.
old-location: devtest\dbgprintex.htm
old-project: devtest
ms.assetid: 0fe82f72-e3dd-49de-a12a-1997e9651bac
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: DbgPrintEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DbgPrintEx
req.alt-loc: NtDll.dll,NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtDll.lib (user mode); NtosKrnl.lib (kernel mode)
req.dll: NtDll.dll (user mode); NtosKrnl.exe (kernel mode)
req.irql: <= DIRQL (see Comments section)
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# DbgPrintEx function



## -description
The <b>DbgPrintEx</b> routine sends a string to the kernel debugger if the  conditions you specify are met.



## -syntax

````
ULONG __cdecl DbgPrintEx(
  _In_ ULONG ComponentId,
  _In_ ULONG Level,
  _In_ PCSTR Format,
       ...   arguments
);
````


## -parameters

### -param ComponentId [in]

Specifies the component calling this routine. This must be one of the component name filter IDs defined in the Dpfilter.h header file. To avoid mixing your driver's output with the output of Windows components, you should use only the following values for <i>ComponentId</i>:

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

Specifies the severity of the message being sent. This can be any 32-bit integer. Values between 0 and 31 (inclusive) are treated differently than values between 32 and 0xFFFFFFFF. For details, see <a href="https://msdn.microsoft.com/2ad320f6-596d-4b4c-bfad-d570c856bcc7">Reading and Filtering Debugging Messages</a>.


### -param Format [in]

Specifies a pointer to the format string to print. The <i>Format</i> string supports most of the <b>printf</b>-style <a href="http://go.microsoft.com/fwlink/p/?linkid=83949">format specification fields</a>. However, the Unicode format codes (<b>%C</b>, <b>%S</b>, <b>%lc</b>, <b>%ls</b>, <b>%wc</b>, <b>%ws</b>, and <b>%wZ</b>) can only be used with IRQL = PASSIVE_LEVEL. The <b>DbgPrintEx</b> routine does not support any of the floating point types (<b>%f</b>, <b>%e</b>, <b>%E</b>, <b>%g</b>, <b>%G</b>, <b>%a</b>, or <b>%A</b>).


### -param arguments 

Specifies arguments for the format string, as in <b>printf</b>.


## -returns
If successful, <b>DbgPrintEx</b> returns the NTSTATUS code STATUS_SUCCESS; otherwise, it returns the appropriate error code.


## -remarks
Only kernel-mode drivers can call the <b>DbgPrintEx</b> routine.

<b>DbgPrint</b> and <b>DbgPrintEx</b> can be called at IRQL&lt;=DIRQL. However, Unicode format codes (<b>%wc</b> and <b>%ws</b>) can be used only at IRQL = PASSIVE_LEVEL. Also, because the debugger uses interprocess interrupts (IPIs) to communicate with other processors, calling <b>DbgPrint</b> at IRQL&gt;DIRQL can cause deadlocks.

<b>DbgPrintEx</b> either passes the specified string to the kernel debugger or does nothing at all, depending on the values of <i>ComponentId</i>, <i>Level</i>, and the corresponding component filter masks. For details, see <a href="https://msdn.microsoft.com/2ad320f6-596d-4b4c-bfad-d570c856bcc7">Reading and Filtering Debugging Messages</a>.

Unless it is absolutely necessary, you should not obtain a string from user input or another process and pass it to <b>DbgPrintEx</b>. If you do use a string that you did not create, you must verify that this is a valid format string, and that the format codes match the argument list in type and quantity. The best coding practice is for all <i>Format</i> strings to be static and defined at compile time.

There is no upper limit to the size of the <i>Format</i> string or the number of arguments. However, any single call to <b>DbgPrintEx</b> will only transmit 512 bytes of information. There is also a limit to the size of the DbgPrint buffer. See <a href="devtest.reading_and_filtering_debugging_messages#ddk_the_dbgprint_buffer_and_the_debugger_tools#ddk_the_dbgprint_buffer_and_the_debugger_tools">The DbgPrint Buffer and the Debugger</a> for details.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-dbgprint.md">DbgPrint</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kdprint.md">KdPrint</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kdprintex.md">KdPrintEx</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-vdbgprintex.md">vDbgPrintEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20DbgPrintEx routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

