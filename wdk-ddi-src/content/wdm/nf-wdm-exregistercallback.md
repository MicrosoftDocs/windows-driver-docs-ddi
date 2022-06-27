---
UID: NF:wdm.ExRegisterCallback
title: ExRegisterCallback function (wdm.h)
description: The ExRegisterCallback routine registers a given callback routine with a given callback object.
old-location: kernel\exregistercallback.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ExRegisterCallback function"]
ms.keywords: ExRegisterCallback, ExRegisterCallback routine [Kernel-Mode Driver Architecture], k102_db841434-fe00-448d-b5bb-2c35d1ad0ec4.xml, kernel.exregistercallback, wdm/ExRegisterCallback
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ExRegisterCallback
 - wdm/ExRegisterCallback
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExRegisterCallback
---

# ExRegisterCallback function


## -description

The <b>ExRegisterCallback</b> routine registers a given callback routine with a given callback object.

## -parameters

### -param CallbackObject [in, out]


A pointer to a callback object obtained from the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-excreatecallback">ExCreateCallback</a> routine.

### -param CallbackFunction [in]


A pointer to a driver-implemented callback routine, which must be nonpageable. The callback routine must conform to the following prototype:


```
VOID
(*PCALLBACK_FUNCTION ) (
    IN PVOID CallbackContext,
    IN PVOID Argument1,
    IN PVOID Argument2
    );
```

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

Callers of <b>ExRegisterCallback</b> must save the returned pointer for use later in a call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exunregistercallback">ExUnregisterCallback</a>. The pointer is required when removing the callback routine from the list of registered callback routines for the callback object.

The meanings of <i>Argument1</i> and <i>Argument2</i> of the registered callback routine depend on the callback object and are defined by the component that created it. The following are the parameters for the <a href="/windows-hardware/drivers/kernel/using-a-system-defined-callback-object">system-defined callback objects</a>:

**\Callback\SetSystemTime**

*Argument1*

<ul>
Not used.
</ul>

*Argument2*

<ul>
Not used.
</ul>

**\Callback\PowerState**

*Argument1*

<ul>
A PO_CB_XXX constant value that is cast to type PVOID.

PO_CB_AC_STATUS — Indicates that the system has changed from A/C to battery power, or vice versa.

PO_CB_LID_SWITCH_STATE — Indicates that the lid switch has changed states.

PO_CB_PROCESSOR_POWER_POLICY — Indicates that the system processor power policy has changed.

PO_CB_SYSTEM_POWER_POLICY — Indicates that the system power policy has changed.

PO_CB_SYSTEM_STATE_LOCK — Indicates that a system power state change is imminent. Drivers in the paging path can register for this callback to receive early warning of such a change, allowing them the opportunity to lock their code in memory before the power state changes.
</ul>

*Argument2*

<ul>
A value of <b>TRUE</b> or <b>FALSE</b> that is cast to type PVOID.

If <i>Argument1</i> is PO_CB_AC_STATUS, <i>Argument2</i> is <b>TRUE</b> if the computer is currently using an A/C power supply, and is <b>FALSE</b> if the computer is running on battery power.

If <i>Argument1</i> is PO_CB_LID_SWITCH_STATE, <i>Argument2</i> is <b>TRUE</b> if the lid is currently open, and is <b>FALSE</b> if the lid is closed.

If <i>Argument1</i> is PO_CB_PROCESSOR_POWER_POLICY, <i>Argument2</i> is not used.

If <i>Argument1</i> is PO_CB_SYSTEM_POWER_POLICY, <i>Argument2</i> is not used.

If <i>Argument1</i> is PO_CB_SYSTEM_STATE_LOCK, <i>Argument2</i> is <b>FALSE</b> if the computer is about to exit system power state S0, and is <b>TRUE</b> if the computer has just reentered S0.
</ul>

**\Callback\ProcessorAdd**

*Argument1*

<ul>
A pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ke_processor_change_notify_context">KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</a> structure that describes the processor change notification event. This pointer is cast to type PVOID. The callback routine must not modify the contents of this structure.
</ul>

*Argument2*

<ul>
A pointer to a variable that contains an NTSTATUS value. This pointer is cast to type PVOID. Under certain conditions, a callback routine can write an error status value to this variable to indicate why the new processor should not be added. A device driver must not change the value of this variable unless all three of the following conditions are true:

An error occurs during the processing of the callback routine that should prevent the new processor from being added.

The value of the <b>State</b> member of the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ke_processor_change_notify_context">KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</a> structure that <i>Argument1</i> points to is <b>KeProcessorAddStartNotify</b>.

The NSTATUS variable that <i>Argument2</i> points to contains the value STATUS_SUCCESS. That is, the callback routine must not overwrite an error status value that was previously written by another callback notification client.
</ul>

Starting with Windows Vista, the <b>\Callback\ProcessorAdd</b> callback object is available to dynamically track changes in the processor population. The <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterprocessorchangecallback">KeRegisterProcessorChangeCallback</a> routine provides similar information, but additionally supports a KE_PROCESSOR_CHANGE_ADD_EXISTING flag that a driver can use to enumerate the processors in the initial multiprocessor system configuration. For drivers that run in Windows Server 2008 and later versions of Windows, use <b>KeRegisterProcessorChangeCallback</b> instead of the <b>\Callback\ProcessorAdd</b> callback object, if possible.

For more information about callback objects, see <a href="/windows-hardware/drivers/kernel/callback-objects">Callback Objects</a>.

The operating system calls registered callback routines at the same IRQL at which the driver that created the callback called the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exnotifycallback">ExNotifyCallback</a> routine.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-excreatecallback">ExCreateCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exnotifycallback">ExNotifyCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exunregistercallback">ExUnregisterCallback</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ke_processor_change_notify_context">KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterprocessorchangecallback">KeRegisterProcessorChangeCallback</a>
