---
UID: NF:fltkernel.FltCheckOplockEx
title: FltCheckOplockEx function
author: windows-driver-content
description: A minifilter driver calls the FltCheckOplockEx routine to synchronize the callback data structure for an IRP-based file I/O operation that has the current opportunistic lock (oplock) state of the file.
old-location: ifsk\fltcheckoplockex.htm
tech.root: ifsk
ms.assetid: 2af1f496-48cf-4f99-a22b-cf7d1837617e
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_a_to_d_3fd997bf-bfdb-4fdd-b6a2-3ade62e0368e.xml, FltCheckOplockEx, FltCheckOplockEx routine [Installable File System Drivers], fltkernel/FltCheckOplockEx, ifsk.fltcheckoplockex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltCheckOplockEx routine is available starting with Windows 7.
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
req.lib: FltMgr.lib
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltCheckOplockEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCheckOplockEx function

## -description

A minifilter driver calls the **FltCheckOplockEx** routine to synchronize the callback data structure for an IRP-based file I/O operation that has the current opportunistic lock (oplock) state of the file.

## -parameters

### -param Oplock [in]

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to [FltInitializeOplock](nf-fltkernel-fltinitializeoplock.md).

### -param CallbackData [in]

A pointer to the callback data [FLT_CALLBACK_DATA](ns-fltkernel-_flt_callback_data.md)structure for the I/O operation.

### -param Flags [in]

A bitmask for the associated file I/O operation. A minifilter driver sets bits to specify the behavior of **FltCheckOplockEx**. The *Flags* parameter has the following options:

#### OPLOCK_FLAG_COMPLETE_IF_OPLOCKED (0x00000001)

Allows an opportunistic lock break to proceed without blocking or pending the operation that caused the oplock break.

#### OPLOCK_FLAG_OPLOCK_KEY_CHECK_ONLY (0x00000002)

Specifies that **FltCheckOplockEx** should only check for an opportunistic lock key on the FILE_OBJECT that is associated with the I/O operation. This I/O operations is represented by the callback data that the *CallbackData* parameter points to. **FltCheckOplockEx** must then add the key if one is provided in the I/O operation. No other oplock processing occurs; that is, no opportunistic lock break will occur.

#### OPLOCK_FLAG_BACK_OUT_ATOMIC_OPLOCK (0x00000004)

Specifies that [FsRtlCheckOplockEx](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcheckoplockex.md) should revert any state that was previously set up through a call to the [FltOplockFsctrl](nf-fltkernel-fltoplockfsctrl.md) routine. **FltOplockFsctrl** is called when an IRP_MJ_CREATE request is processed. This IRP_MJ_CREATE request specifies the FILE_OPEN_REQUIRING_OPLOCK flag in the create options parameter. The OPLOCK_FLAG_BACK_OUT_ATOMIC_OPLOCK flag is typically used in final processing of such a create request when it previously failed.

#### OPLOCK_FLAG_IGNORE_OPLOCK_KEYS (0x00000008)

Allows all opportunistic lock breaks to proceed regardless of the opportunistic lock key.

### -param Context [in, optional]

A pointer to caller-defined context information to be passed to the callback routines that *WaitCompletionRoutine* and *PrePostCallbackDataRoutine* point to. The Filter Manager treats this information as opaque.

### -param WaitCompletionRoutine [in, optional]

A pointer to a caller-supplied callback routine. If an oplock break is in progress, the Filter Manager calls this routine when the oplock break is completed. This parameter is optional and can be **NULL**. If it is **NULL**, the caller is put into a wait state until the oplock break is completed.

This routine is declared as follows:

```C
typedef VOID
(*PFLTOPLOCK_WAIT_COMPLETE_ROUTINE) (
      IN PFLT_CALLBACK_DATA CallbackData,
      IN PVOID Context
      );
```

This routine has the following parameters:

#### CallbackData

A pointer to the callback data structure for the I/O operation.

#### Context

A context information pointer that was passed in the *Context* parameter to **FltCheckOplockEx**.

### -param PrePostCallbackDataRoutine [in, optional]

A pointer to a caller-supplied callback routine to be called if the I/O operation is posted to a work queue. This parameter is optional and can be **NULL**.

This routine is declared as follows:

```C
typedef VOID
(*PFLTOPLOCK_PREPOST_CALLBACKDATA_ROUTINE) (
      IN PFLT_CALLBACK_DATA CallbackData,
      IN PVOID Context
      );
```

#### CallbackData

A pointer to the callback data structure for the I/O operation.

#### Context

A context information pointer that was passed in the *Context* parameter to **FltCheckOplockEx**.

## -returns

**FltCheckOplockEx** returns one of the following FLT_PREOP_CALLBACK_STATUS codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FLT_PREOP_COMPLETE</b></dt>
</dl>
</td>
<td width="60%">
<b>FltCheckOplockEx</b> encountered a pool allocation failure, or a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcheckoplockex">FsRtlCheckOplockEx</a> function returned an error. <b>FltCheckOplockEx</b> sets the error code in the <b>Status</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure of the <b>IoStatus</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> callback data structure. The <i>CallbackData</i> parameter points to this FLT_CALLBACK_DATA structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FLT_PREOP_PENDING</b></dt>
</dl>
</td>
<td width="60%">
An oplock break was initiated, which caused the Filter Manager to post the I/O operation to a work queue. The I/O operation is represented by the callback data that the <i>CallbackData</i> parameter points to.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FLT_PREOP_SUCCESS_WITH_CALLBACK</b></dt>
</dl>
</td>
<td width="60%">
The callback data that the <i>CallbackData</i> parameter points to was not pended, and the I/O operation was performed immediately. Be aware that if the caller specified OPLOCK_FLAG_COMPLETE_IF_OPLOCKED in the <i>Flags</i> parameter, an oplock break might actually be in progress even though the I/O operation was not pended. To determine whether this is the situation, the caller should check for STATUS_OPLOCK_BREAK_IN_PROGRESS in the <b>Status</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure of the <b>IoStatus</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a> callback data structure.

</td>
</tr>
</table>

## -remarks

A minifilter driver calls **FltCheckOplockEx** to synchronize an IRP-based I/O operation with the current oplock state of a file according to the following conditions:

* If the I/O operation will cause the oplock to break, the oplock break is initiated.

* If the I/O operation cannot continue until the oplock break is complete, **FltCheckOplockEx** returns FLT_PREOP_PENDING and calls the callback routine that the *PrePostCallbackDataRoutine* parameter points to.

* If a minifilter driver uses oplocks, it must call **FltCheckOplockEx** from any preoperation callback ([PFLT_PRE_OPERATION_CALLBACK](nc-fltkernel-pflt_pre_operation_callback.md)) routine for I/O operations that can cause oplock breaks. This rule applies to the following types of I/O operations, because these operations can cause oplock breaks:

  * IRP_MJ_CLEANUP

  * IRP_MJ_CREATE

  * IRP_MJ_FILE_SYSTEM_CONTROL

  * IRP_MJ_FLUSH_BUFFERS

  * IRP_MJ_LOCK_CONTROL

  * IRP_MJ_READ

  * IRP_MJ_SET_INFORMATION

  * IRP_MJ_WRITE

The I/O operation must be an IRP-based I/O operation. To determine whether a given callback data structure represents an IRP-based I/O operation, use the [FLT_IS_IRP_OPERATION](https://msdn.microsoft.com/library/windows/hardware/ff544654) macro.

Minifilters must not call **FltCheckOplockEx** again within the callback specified in *WaitCompletionRoutine*. Doing so can result in a deadlock condition if the oplock package calls the completion callback before **FltCheckOplockEx** returns.

For more information about opportunistic locks, see the Microsoft Windows SDK documentation.

## -see-also

[FLT_CALLBACK_DATA](ns-fltkernel-_flt_callback_data.md)

[FLT_IS_IRP_OPERATION](https://msdn.microsoft.com/library/windows/hardware/ff544654)

[FltInitializeOplock](nf-fltkernel-fltinitializeoplock.md)

[FltOplockFsctrl](nf-fltkernel-fltoplockfsctrl.md)

[FsRtlCheckOplockEx](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcheckoplockex.md)

[IO_STATUS_BLOCK](https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_status_block)

[PFLT_PRE_OPERATION_CALLBACK](nc-fltkernel-pflt_pre_operation_callback.md)
