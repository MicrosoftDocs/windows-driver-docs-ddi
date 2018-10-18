---
UID: NF:wdm.ExRegisterCallback
title: ExRegisterCallback function
author: windows-driver-content
description: The ExRegisterCallback routine registers a given callback routine with a given callback object.
old-location: kernel\exregistercallback.htm
tech.root: kernel
ms.assetid: 4537447a-17d5-4431-929c-7a8fda0f2986
ms.date: 04/30/2018
ms.keywords: ExRegisterCallback, ExRegisterCallback routine [Kernel-Mode Driver Architecture], k102_db841434-fe00-448d-b5bb-2c35d1ad0ec4.xml, kernel.exregistercallback, wdm/ExRegisterCallback
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExApcLte2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExRegisterCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExRegisterCallback function


## -description


The <b>ExRegisterCallback</b> routine registers a given callback routine with a given callback object.


## -parameters




### -param CallbackObject [in, out]

A pointer to a callback object obtained from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544560">ExCreateCallback</a> routine.


### -param CallbackFunction [in]

A pointer to a driver-implemented callback routine, which must be nonpageable. The callback routine must conform to the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
(*PCALLBACK_FUNCTION ) (
    IN PVOID CallbackContext,
    IN PVOID Argument1,
    IN PVOID Argument2
    );</pre>
</td>
</tr>
</table></span></div>
The callback routine parameters are as follows:





#### CallbackContext

A pointer to a driver-supplied context area as specified in the <i>CallbackContext</i> parameter of <b>ExRegisterCallback</b>.



#### Argument1

A pointer to a parameter defined by the callback object.



#### Argument2

A pointer to a parameter defined by the callback object.


### -param CallbackContext [in, optional]

A pointer to a caller-defined structure of data items to be passed as the context parameter of the callback routine each time it is called. Typically the context is part of the caller's device object extension.


## -returns



<b>ExRegisterCallback</b> returns a pointer to a callback registration handle that should be treated as opaque and reserved for system use. This pointer is <b>NULL</b> if <b>ExRegisterCallback</b> completes with an error.




## -remarks



A driver calls <b>ExRegisterCallback</b> to register a callback routine with a specified callback object.

If the object allows only one registered callback routine, and such a routine is already registered, <b>ExRegisterCallback</b> returns <b>NULL</b>.

Callers of <b>ExRegisterCallback</b> must save the returned pointer for use later in a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545649">ExUnregisterCallback</a>. The pointer is required when removing the callback routine from the list of registered callback routines for the callback object.

The meanings of <i>Argument1</i> and <i>Argument2</i> of the registered callback routine depend on the callback object and are defined by the component that created it. The following are the parameters for the <a href="https://msdn.microsoft.com/1f1a2fc1-e698-41f7-84e4-9db091def690">system-defined callback objects</a>:



Starting with Windows Vista, the <b>\Callback\ProcessorAdd</b> callback object is available to dynamically track changes in the processor population. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff553120">KeRegisterProcessorChangeCallback</a> routine provides similar information, but additionally supports a KE_PROCESSOR_CHANGE_ADD_EXISTING flag that a driver can use to enumerate the processors in the initial multiprocessor system configuration. For drivers that run in Windows Server 2008 and later versions of Windows, use <b>KeRegisterProcessorChangeCallback</b> instead of the <b>\Callback\ProcessorAdd</b> callback object, if possible.

For more information about callback objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540718">Callback Objects</a>.

The operating system calls registered callback routines at the same IRQL at which the driver that created the callback called the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545489">ExNotifyCallback</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544560">ExCreateCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545489">ExNotifyCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545649">ExUnregisterCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554229">KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553120">KeRegisterProcessorChangeCallback</a>
 

 

