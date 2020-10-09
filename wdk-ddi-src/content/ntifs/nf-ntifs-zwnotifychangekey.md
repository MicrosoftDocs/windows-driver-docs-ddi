---
UID: NF:ntifs.ZwNotifyChangeKey
title: ZwNotifyChangeKey function (ntifs.h)
description: The ZwNotifyChangeKey routine allows a driver to request notification when a registry key changes.
old-location: kernel\zwnotifychangekey.htm
tech.root: kernel
ms.assetid: 660c04b0-499b-40e7-94c2-5cb457e93f00
ms.date: 04/30/2018
keywords: ["ZwNotifyChangeKey function"]
ms.keywords: NtNotifyChangeKey, ZwNotifyChangeKey, ZwNotifyChangeKey routine [Kernel-Mode Driver Architecture], k111_e9219ad8-c702-45a2-97f1-a195c1aa8b89.xml, kernel.zwnotifychangekey, ntifs/NtNotifyChangeKey, ntifs/ZwNotifyChangeKey
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwNotifyChangeKey
 - ntifs/ZwNotifyChangeKey
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwNotifyChangeKey
 - NtNotifyChangeKey
---

# ZwNotifyChangeKey function


## -description

The <b>ZwNotifyChangeKey</b> routine allows a driver to request notification when a registry key changes.

## -parameters

### -param KeyHandle 

[in]
Handle to the key to register a notification routine for. This handle is created by a successful call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>. The caller must have specified KEY_NOTIFY access.

### -param Event 

[in, optional]
Handle to a caller-created event. If not <b>NULL</b>, the caller is placed into a wait state until the operation succeeds, at which time the event is set to the Signaled state.

### -param ApcRoutine 

[in, optional]
 For a user-mode call, this parameter points to a caller-supplied APC routine that is run after the operation is completed. This parameter is optional and can be <b>NULL</b>.

  For a kernel-mode call, this parameter must be <b>NULL</b>.

### -param ApcContext 

[in, optional]
The meaning of this parameter depends on whether the routine is called from kernel mode or from user mode. For a kernel-mode call, set this parameter to one of the following <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_work_queue_type">WORK_QUEUE_TYPE</a> enumeration values:

<ul>
<li>
CriticalWorkQueue

</li>
<li>
DelayedWorkQueue

</li>
</ul>
The parameter value must be cast to type PVOID. For a user-mode call, this parameter points to a caller-specified context for the APC routine. This value is passed to the APC routine when it is run.

### -param IoStatusBlock 

[out]
Pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure that contains the final status and information about the operation. For successful calls that return data, the number of bytes written to <i>Buffer</i> is supplied in <i>IoStatusBlock</i>-><b>Information</b>.

### -param CompletionFilter 

[in]
Bitmask of operations that cause the driver to be notified. Specify one or more of the following flags:





#### REG_NOTIFY_CHANGE_NAME

Notify the caller if a subkey is added or deleted.



#### REG_NOTIFY_CHANGE_ATTRIBUTES

Notify the caller of changes to the attributes of the key, such as the security descriptor information.



#### REG_NOTIFY_CHANGE_LAST_SET

Notify the caller of changes to a value of the key. This can include adding or deleting a value, or changing an existing value. (The caller receives no notification if the new value written to the key matches the previous value of the key.)



#### REG_NOTIFY_CHANGE_SECURITY

Notify the caller of changes to the security descriptor of the key.

### -param WatchTree 

[in]
If <b>TRUE</b>, the driver is notified about changes to all subkeys of the specified key. If <b>FALSE</b>, the driver is only notified for changes to the specified key.

### -param Buffer 

[out, optional]
Reserved. Specify <b>NULL</b>.

### -param BufferSize 

[in]
Reserved. Specify zero.

### -param Asynchronous 

[in]
If <b>FALSE</b>, the routine does not return until the specified event occurs. If <b>TRUE</b>, the routine returns immediately.

## -returns

The <b>ZwNotifyChangeKey</b> routine returns STATUS_SUCCESS on success, or the appropriate NTSTATUS value otherwise. If the caller specifies <b>TRUE</b> for the <i>Asynchronous</i> parameter, and the event has not yet occurred, the routine returns STATUS_PENDING.

## -remarks

If the call to the <b>ZwNotifyChangeKey</b> function occurs in user mode, you should use the name "<b>NtNotifyChangeKey</b>" instead of "<b>ZwNotifyChangeKey</b>". 

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a>



<a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_work_queue_item">WORK_QUEUE_ITEM</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_work_queue_type">WORK_QUEUE_TYPE</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>