---
UID: NF:wdm.ExRegisterCallback
title: ExRegisterCallback function
author: windows-driver-content
description: The ExRegisterCallback routine registers a given callback routine with a given callback object.
old-location: kernel\exregistercallback.htm
old-project: kernel
ms.assetid: 4537447a-17d5-4431-929c-7a8fda0f2986
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExRegisterCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExRegisterCallback
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IrqlExApcLte2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExRegisterCallback function



## -description
The <b>ExRegisterCallback</b> routine registers a given callback routine with a given callback object.



## -syntax

````
PVOID ExRegisterCallback(
  _Inout_  PCALLBACK_OBJECT   CallbackObject,
  _In_     PCALLBACK_FUNCTION CallbackFunction,
  _In_opt_ PVOID              CallbackContext
);
````


## -parameters

### -param CallbackObject [in, out]

A pointer to a callback object obtained from the <a href="..\wdm\nf-wdm-excreatecallback.md">ExCreateCallback</a> routine.


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




### -param CallbackContext

A pointer to a driver-supplied context area as specified in the <i>CallbackContext</i> parameter of <b>ExRegisterCallback</b>.


### -param Argument1

A pointer to a parameter defined by the callback object.


### -param Argument2

A pointer to a parameter defined by the callback object.

</dd>
</dl>

### -param CallbackContext [in, optional]

A pointer to a caller-defined structure of data items to be passed as the context parameter of the callback routine each time it is called. Typically the context is part of the caller's device object extension.


## -returns
<b>ExRegisterCallback</b> returns a pointer to a callback registration handle that should be treated as opaque and reserved for system use. This pointer is <b>NULL</b> if <b>ExRegisterCallback</b> completes with an error.


## -remarks
A driver calls <b>ExRegisterCallback</b> to register a callback routine with a specified callback object.

If the object allows only one registered callback routine, and such a routine is already registered, <b>ExRegisterCallback</b> returns <b>NULL</b>.

Callers of <b>ExRegisterCallback</b> must save the returned pointer for use later in a call to <a href="..\wdm\nf-wdm-exunregistercallback.md">ExUnregisterCallback</a>. The pointer is required when removing the callback routine from the list of registered callback routines for the callback object.

The meanings of <i>Argument1</i> and <i>Argument2</i> of the registered callback routine depend on the callback object and are defined by the component that created it. The following are the parameters for the <a href="https://msdn.microsoft.com/1f1a2fc1-e698-41f7-84e4-9db091def690">system-defined callback objects</a>:



Not used.

A PO_CB_<i>XXX</i> constant value that is cast to type PVOID.

PO_CB_AC_STATUS — Indicates that the system has changed from A/C to battery power, or vice versa.

PO_CB_LID_SWITCH_STATE — Indicates that the lid switch has changed states.

PO_CB_PROCESSOR_POWER_POLICY — Indicates that the system processor power policy has changed.

PO_CB_SYSTEM_POWER_POLICY — Indicates that the system power policy has changed.

PO_CB_SYSTEM_STATE_LOCK — Indicates that a system power state change is imminent. Drivers in the paging path can register for this callback to receive early warning of such a change, allowing them the opportunity to lock their code in memory before the power state changes.

A value of <b>TRUE</b> or <b>FALSE</b> that is cast to type PVOID.

If <i>Argument1</i> is PO_CB_AC_STATUS, <i>Argument2</i> is <b>TRUE</b> if the computer is currently using an A/C power supply, and is <b>FALSE</b> if the computer is running on battery power.

If <i>Argument1</i> is PO_CB_LID_SWITCH_STATE, <i>Argument2</i> is <b>TRUE</b> if the lid is currently open, and is <b>FALSE</b> if the lid is closed.

If <i>Argument1</i> is PO_CB_PROCESSOR_POWER_POLICY, <i>Argument2</i> is not used. 

If <i>Argument1</i> is PO_CB_SYSTEM_POWER_POLICY, <i>Argument2</i> is not used.

If <i>Argument1</i> is PO_CB_SYSTEM_STATE_LOCK, <i>Argument2</i> is <b>FALSE</b> if the computer is about to exit system power state S0, and is <b>TRUE</b> if the computer has just reentered S0.

A pointer to a <a href="..\wdm\ns-wdm-_ke_processor_change_notify_context.md">KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</a> structure that describes the processor change notification event. This pointer is cast to type PVOID. The callback routine must not modify the contents of this structure.

A pointer to a variable that contains an NTSTATUS value. This pointer is cast to type PVOID. Under certain conditions, a callback routine can write an error status value to this variable to indicate why the new processor should not be added. A device driver must not change the value of this variable unless all three of the following conditions are true:

An error occurs during the processing of the callback routine that should prevent the new processor from being added.

The value of the <b>State</b> member of the <a href="..\wdm\ns-wdm-_ke_processor_change_notify_context.md">KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</a> structure that <i>Argument1</i> points to is <b>KeProcessorAddStartNotify</b>.

The NSTATUS variable that <i>Argument2</i> points to contains the value STATUS_SUCCESS. That is, the callback routine must not overwrite an error status value that was previously written by another callback notification client.

Starting with Windows Vista, the <b>\Callback\ProcessorAdd</b> callback object is available to dynamically track changes in the processor population. The <a href="..\wdm\nf-wdm-keregisterprocessorchangecallback.md">KeRegisterProcessorChangeCallback</a> routine provides similar information, but additionally supports a KE_PROCESSOR_CHANGE_ADD_EXISTING flag that a driver can use to enumerate the processors in the initial multiprocessor system configuration. For drivers that run in Windows Server 2008 and later versions of Windows, use <b>KeRegisterProcessorChangeCallback</b> instead of the <b>\Callback\ProcessorAdd</b> callback object, if possible.

For more information about callback objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540718">Callback Objects</a>.

The operating system calls registered callback routines at the same IRQL at which the driver that created the callback called the <a href="..\wdm\nf-wdm-exnotifycallback.md">ExNotifyCallback</a> routine.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-excreatecallback.md">ExCreateCallback</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exnotifycallback.md">ExNotifyCallback</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exunregistercallback.md">ExUnregisterCallback</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_ke_processor_change_notify_context.md">KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keregisterprocessorchangecallback.md">KeRegisterProcessorChangeCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExRegisterCallback routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

