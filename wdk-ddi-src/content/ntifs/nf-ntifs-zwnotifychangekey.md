---
UID: NF:ntifs.ZwNotifyChangeKey
title: ZwNotifyChangeKey function (ntifs.h)
description: Learn more about the ZwNotifyChangeKey function.
tech.root: kernel
ms.date: 09/25/2025
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
---

# ZwNotifyChangeKey function

## -description

The **ZwNotifyChangeKey** routine allows a driver to request notification when a registry key changes.

## -parameters

### -param KeyHandle [in]

Handle to the key to register a notification routine for. This handle is created by a successful call to [**ZwCreateKey**](../wdm/nf-wdm-zwcreatekey.md) or [**ZwOpenKey**](../wdm/nf-wdm-zwopenkey.md). The caller must have specified KEY_NOTIFY access.

### -param Event [in, optional]

Optional handle to a caller-created event to be set to the Signaled state when the operation completes. If not NULL, the caller is placed into a wait state until the operation succeeds, at which time the event is set to the Signaled state.

### -param ApcRoutine [in, optional]

Pointer to a caller-supplied APC routine to run after the operation completes. This parameter is optional and can be NULL.

* For a kernel-mode call, set this parameter to a pointer to a [**WORK_QUEUE_ITEM**](../wdm/ns-wdm-_work_queue_item.md) struct

### -param ApcContext [in, optional]

Pointer to pass as an argument to the APC routine that **ApcRoutine** points to. This argument is required if **ApcRoutine** isn't NULL, and must be cast to type PVOID. Otherwise, if **ApcRoutine** is NULL, set this parameter to NULL, too.

The meaning of this parameter depends on whether the routine is called from kernel mode or from user mode:

* For a kernel-mode call, set this parameter to one of the following [**WORK_QUEUE_TYPE**](../wdm/ne-wdm-_work_queue_type.md) enumeration values:

  * CriticalWorkQueue
  * DelayedWorkQueue

* For a user-mode call, this parameter points to a caller-specified context for the APC routine.

### -param IoStatusBlock [out]

Pointer to an [**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md) structure that contains the final status and information about the operation. For successful calls that return data, the number of bytes written to **Buffer** is supplied in **IoStatusBlock**->**Information**.

### -param CompletionFilter [in]

Bitmask of operations that cause the driver to be notified. Specify one or more of the following flags:

| Value | Meaning |
| ----- | ------- |
| REG_NOTIFY_CHANGE_NAME       | Notify the caller if a subkey is added or deleted. |
| REG_NOTIFY_CHANGE_ATTRIBUTES | Notify the caller of changes to the attributes of the key, such as the security descriptor information. |
| REG_NOTIFY_CHANGE_LAST_SET   | Notify the caller of changes to a value of the key. This can include adding or deleting a value, or changing an existing value. (The caller receives no notification if the new value written to the key matches the previous value of the key.) |
| REG_NOTIFY_CHANGE_SECURITY   | Notify the caller of changes to the security descriptor of the key. |

### -param WatchTree [in]

If TRUE, the driver is notified about changes to all subkeys of the specified key. If FALSE, the driver is only notified for changes to the specified key.

### -param Buffer [out, optional]

Reserved. Specify NULL.

### -param BufferSize [in]

Reserved. Specify zero.

### -param Asynchronous [in]

If FALSE, the routine does not return until the specified event occurs. If TRUE, the routine returns immediately.

## -returns

The **ZwNotifyChangeKey** routine returns STATUS_SUCCESS on success, or the appropriate NTSTATUS value otherwise. If the caller specifies TRUE for the **Asynchronous** parameter, and the event has not yet occurred, the routine returns STATUS_PENDING.

## -remarks

**ZwNotifyChangeKey** monitors a registry key for changes and notifies the caller when modifications occur.

The routine monitors the specified key (and optionally its subtree) for changes based on the **CompletionFilter** flags. When a change occurs, the system notifies the caller via event signaling, APC callback, or synchronous completion.

This is a one-time notification. After a registry change triggers the notification, you must call **ZwNotifyChangeKey** again to continue monitoring.

The key must be opened with KEY_NOTIFY access before calling this routine.

For asynchronous operation (**Asynchronous** = TRUE):

* If **Event** is specified, it will be signaled when changes occur. If **Event** is NULL, then **KeyHandle** is set to the Signaled state.
* If **ApcRoutine** is specified, it will be called with **ApcContext** and **IoStatusBlock**.
* If neither is specified, the **KeyHandle** itself becomes signalable.

For synchronous operation (**Asynchronous** = FALSE):

* The call blocks until a change occurs.
* **Event**, **ApcRoutine**, and **ApcContext** parameters are ignored.

The notification session ends when **KeyHandle** is closed.

Note: **CompletionFilter** and **WatchTree** are set on the first call and apply to all subsequent calls using the same **KeyHandle**. These parameters are ignored on subsequent calls.

Registry notifications hold handles that will prevent hive unload operations (such as [**RegUnloadKey**](/windows/win32/api/winreg/nf-winreg-regunloadkeyw)) until closed. Currently, there is no mechanism for a driver to have a notification that won’t block **RegUnloadKey**. Drivers can try to proactively cancel notifications when the monitored process or user session ends to avoid blocking legitimate hive management operations.

If the call to the **ZwNotifyChangeKey** function occurs in user mode, you should use the name "**NtNotifyChangeKey**" instead of "**ZwNotifyChangeKey**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md)

[**WORK_QUEUE_ITEM**](../wdm/ns-wdm-_work_queue_item.md)

[**WORK_QUEUE_TYPE**](../wdm/ne-wdm-_work_queue_type.md)

[**ZwCreateKey**](../wdm/nf-wdm-zwcreatekey.md)

[**ZwOpenKey**](../wdm/nf-wdm-zwopenkey.md)
