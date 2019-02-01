---
UID: NF:wdm.KdPrint
title: KdPrint macro (wdm.h)
description: The KdPrint macro sends a message to the kernel debugger.
old-location: devtest\kdprint.htm
tech.root: devtest
ms.assetid: 4a2ab12b-ee89-462d-821a-0a2db20cc36c
ms.date: 02/23/2018
ms.keywords: DebugFns_630aea64-3f51-4c73-8575-00a507846ab9.xml, KdPrint, KdPrint function [Driver Development Tools], devtest.kdprint, wdm/KdPrint
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later.
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
req.lib: NtosKrnl.lib (See DbgPrint.)
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KdPrint
product:
- Windows
targetos: Windows
req.typenames: 
---

# KdPrint macro


## -description


The <b>KdPrint</b> macro sends a message to the kernel debugger. 

In Windows Vista and later versions of Windows, <b>KdPrint</b> sends a message only if the conditions you specify apply (see the <a href="https://docs.microsoft.com/">Remarks</a> section for information).

A call to <b>KdPrint</b> requires double parentheses.


## -parameters




### -param _x_ [in]

Specifies a pointer to the format string to print. The <i>Format</i> string supports most of the <b>printf</b>-style <a href="https://go.microsoft.com/fwlink/p/?linkid=83949">format specification fields</a>. However, the Unicode format codes (<b>%C</b>, <b>%S</b>, <b>%lc</b>, <b>%ls</b>, <b>%wc</b>, <b>%ws</b>, and <b>%wZ</b>) can only be used with IRQL = PASSIVE_LEVEL. The <b>KdPrint</b> routine does not support any of the floating point types (<b>%f</b>, <b>%e</b>, <b>%E</b>, <b>%g</b>, <b>%G</b>, <b>%a</b>, or <b>%A</b>).


## -remarks



<h3><a id="remarks"></a><a id="REMARKS"></a></h3>
<b>KdPrint</b> is identical to the <b>DbgPrint</b> routine in code that is compiled for a debug configuration.  This routine has no effect if compiled for a release configuration. Only kernel-mode drivers can call the <b>KdPrint</b> routine.

In Microsoft Windows Server 2003 and earlier versions of Windows, the <b>DbgPrint</b> routine sends a message to the kernel debugger. In Windows Vista and later versions of Windows, <b>KdPrint</b> sends a message only if certain conditions apply. Specifically, it behaves like <a href="https://msdn.microsoft.com/library/windows/hardware/ff548100">KdPrintEx</a> with the DEFAULT component and a message importance level of DPFLTR_INFO_LEVEL. In other words, the following two function calls are identical:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>KdPrint (( Format, arguments ))

KdPrintEx (( DPFLTR_DEFAULT_ID, DPFLTR_INFO_LEVEL, Format, arguments ))</pre>
</td>
</tr>
</table></span></div>
For more information about message filtering, components, and message importance level, see <a href="https://msdn.microsoft.com/2ad320f6-596d-4b4c-bfad-d570c856bcc7">Reading and Filtering Debugging Messages</a>.

<div class="alert"><b>Note</b>    Regardless of which version of Windows you are using, it is recommended that you use <b>KdPrintEx</b> instead of <b>KdPrint</b>, since <b>KdPrintEx</b> allows you to control the conditions under which the message is sent.</div>
<div> </div>
Unless it is absolutely necessary, you should not obtain a string from user input or another process and pass it to <b>KdPrint</b>. If you do use a string that you did not create, you must verify that this is a valid format string, and that the format codes match the argument list in type and quantity. The best coding practice is for all <i>Format</i> strings to be static and defined at compile time.

There is no upper limit to the size of the <i>Format</i> string or the number of arguments. However, any single call to <b>KdPrint</b> will only transmit 512 bytes of information. There is also a limit to the size of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543632">DbgPrint</a> buffer. See <a href="https://msdn.microsoft.com/2ad320f6-596d-4b4c-bfad-d570c856bcc7">The DbgPrint Buffer and the Debugger</a> for details.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543632">DbgPrint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543634">DbgPrintEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548100">KdPrintEx</a>
 

 

