---
UID: NF:wdm.ExCreateCallback
title: ExCreateCallback function (wdm.h)
description: The ExCreateCallback routine either creates a new callback object or opens an existing callback object on behalf of the caller.
old-location: kernel\excreatecallback.htm
tech.root: kernel
ms.assetid: a8532a6d-2b7f-4ed6-a2e4-6157d5e842ff
ms.date: 04/30/2018
keywords: ["ExCreateCallback function"]
ms.keywords: ExCreateCallback, ExCreateCallback routine [Kernel-Mode Driver Architecture], k102_7c7f1024-8ae7-4925-91f3-add4fcb452b7.xml, kernel.excreatecallback, wdm/ExCreateCallback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExPassive, HwStorPortProhibitedDDIs
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
 - ExCreateCallback
 - wdm/ExCreateCallback
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExCreateCallback
---

# ExCreateCallback function


## -description

The <b>ExCreateCallback</b> routine either creates a new callback object or opens an existing callback object on behalf of the caller.

## -parameters

### -param CallbackObject 

[out]
A pointer to a location that receives a pointer to a callback object, which is an opaque, system structure. If the <b>ExCreateCallback</b> call succeeds, the routine writes the address of the newly created or opened callback object to this location. The callback object pointer obtained from this routine can be supplied as a parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exregistercallback">ExRegisterCallback</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exnotifycallback">ExNotifyCallback</a> routine.

### -param ObjectAttributes 

[in]
A pointer to an <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> structure that contains the callback object's attributes. This structure was previously initialized by the <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a> routine.

### -param Create 

[in]
Whether to create a callback object. Set to <b>TRUE</b> to create a new callback object if the requested object cannot be opened. Otherwise, set to <b>FALSE</b>.

### -param AllowMultipleCallbacks 

[in]
Whether a newly created callback object should allow multiple registered callback routines. Set to <b>TRUE</b> to allow multiple registered callback routines. Otherwise, set to <b>FALSE</b>. This parameter is ignored when <i>Create</i> is <b>FALSE</b> or when opening an existing object.

## -returns

<b>ExCreateCallback</b> returns STATUS_SUCCESS if a callback object was opened or created. Otherwise, it returns an NTSTATUS error code to indicate the nature of the failure.

## -remarks

A driver calls <b>ExCreateCallback</b> to create a new callback object or to open an existing callback object. After the object has been created or opened, other components can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exregistercallback">ExRegisterCallback</a> routine to register callback routines with the callback object.

Before calling <b>ExCreateCallback</b>, the driver must call <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a> to initialize the <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> structure for the callback object. Unnamed callback objects are not permitted. The caller must specify a name for the object; otherwise, the call fails with STATUS_UNSUCCESSFUL. The caller should specify the OBJ_PERMANENT attribute in the callback object to prevent the object from being deleted before it can be registered with the object manager. The caller should also specify any other attributes, such as OBJ_CASE_INSENSITIVE, that might be needed.

When all operations have been completed with the callback object, the driver must delete the object to prevent a memory leak. For information about deleting an object  that was created with the OBJ_PERMANENT object attribute, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>.

The following table shows the callback objects that the operating system creates for use by drivers.

<table>
<tr>
<th>Callback object name</th>
<th>Usage</th>
</tr>
<tr>
<td>
\Callback\SetSystemTime

</td>
<td>
The operating system calls any callback routines registered for this object whenever the system time changes.

</td>
</tr>
<tr>
<td>
\Callback\PowerState

</td>
<td>
The operating system calls any callback routines registered for this object  whenever certain system power characteristics change. When a driver registers for callback notification (by calling <b>ExRegisterCallback</b>), it can specify the changes for which it should be notified.

</td>
</tr>
</table>
 

For more information about callback objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/callback-objects">Callback Objects</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exnotifycallback">ExNotifyCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exregistercallback">ExRegisterCallback</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>

