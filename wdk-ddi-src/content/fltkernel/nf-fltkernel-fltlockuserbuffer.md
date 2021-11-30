---
UID: NF:fltkernel.FltLockUserBuffer
title: FltLockUserBuffer function (fltkernel.h)
description: The FltLockUserBuffer routine locks the user buffer for a given I/O operation.
old-location: ifsk\fltlockuserbuffer.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltLockUserBuffer function"]
ms.keywords: FltApiRef_e_to_o_7d39ba00-c97d-4adb-a0e1-a019ca4056b0.xml, FltLockUserBuffer, FltLockUserBuffer routine [Installable File System Drivers], fltkernel/FltLockUserBuffer, ifsk.fltlockuserbuffer
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltLockUserBuffer
 - fltkernel/FltLockUserBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltLockUserBuffer
---

# FltLockUserBuffer function

## -description

The **FltLockUserBuffer** routine locks the user buffer for a given I/O operation.

## -parameters

### -param CallbackData [in]

Pointer to the callback data  structure for the I/O operation ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)).

## -returns

If the user buffer is successfully locked, **FltLockUserBuffer** returns STATUS_SUCCESS. (This is the case even if the buffer was already locked by a previous call to **FltLockUserBuffer**.) Otherwise, it returns an appropriate NTSTATUS value, such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_INSUFFICIENT_RESOURCES | **FltLockUserBuffer** encountered a pool allocation failure. This is an error code. |
| STATUS_INVALID_PARAMETER      | The I/O operation is not one of the operations listed in the following Remarks section. This is an error code. |

## -remarks

A minifilter driver calls **FltLockUserBuffer** to lock the user buffer for one of the following I/O operations:

* IRP_MJ_DEVICE_CONTROL
* IRP_MJ_DIRECTORY_CONTROL
* IRP_MJ_FILE_SYSTEM_CONTROL
* IRP_MJ_INTERNAL_DEVICE_CONTROL
* IRP_MJ_QUERY_EA
* IRP_MJ_QUERY_QUOTA
* IRP_MJ_QUERY_SECURITY
* IRP_MJ_READ
* IRP_MJ_SET_EA
* IRP_MJ_SET_QUOTA
* IRP_MJ_WRITE

**FltLockUserBuffer** determines the appropriate access method (IoReadAccess, IoWriteAccess, or IoModifyAccess) to apply for the locked buffer based on the type of I/O operation.

**FltLockUserBuffer** sets the **MdlAddress** (or **OutputMdlAddress**) member  in the callback data parameter structure ([**FLT_PARAMETERS**](ns-fltkernel-_flt_parameters.md)) to point to the MDL for the locked pages. If there is no MDL, **FltLockUserBuffer** allocates one.

If the callback data parameter structure contains a system buffer and does not contain a user buffer, **FltLockUserBuffer** locks the system buffer. If there is no MDL for the system buffer, **FltLockUserBuffer** allocates one.

If **FltLockUserBuffer** is called from a preoperation callback routine ([**PFLT_PRE_OPERATION_CALLBACK**](nc-fltkernel-pflt_pre_operation_callback.md)) and it allocates an MDL, **FltLockUserBuffer** sets the FLTFL_CALLBACK_DATA_DIRTY flag in the callback data structure ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) so that the I/O system frees the MDL when the I/O operation is completed.

To conserve system page table entries (PTE), **FltLockUserBuffer** does not map the locked pages. After calling **FltLockUserBuffer**, the caller must call [MmGetSystemAddressForMdlSafe](../wdm/nf-wdm-mmgetsystemaddressformdlsafe.md), passing the **MdlAddress** (or **OutputMdlAddress**) member in the callback data parameter structure as the value of the **Mdl** parameter, to get a system buffer that represents this memory.

Use of **FltLockUserBuffer** can slow system performance. This is not because of **FltLockUserBuffer** itself, but rather because of the performance penalty incurred by [MmGetSystemAddressForMdlSafe](../wdm/nf-wdm-mmgetsystemaddressformdlsafe.md).

The caller can be running in any process context. **FltLockUserBuffer** automatically locks the buffer in the correct process context.

When the callback data structure is freed, the locked buffer is automatically unlocked, and the MDL is freed. The caller should never free the MDL; the I/O system does this automatically.

**FltLockUserBuffer** can be called for fast I/O and IRP-based operations.

## -see-also

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FLT_IS_FASTIO_OPERATION**](nf-fltkernel-flt_is_fastio_operation.md)

[**FLT_IS_IRP_OPERATION**](/previous-versions/ff544654(v=vs.85))

[**FLT_IS_SYSTEM_BUFFER**](/previous-versions/ff544663(v=vs.85))

[**FLT_PARAMETERS**](ns-fltkernel-_flt_parameters.md)

[**FLT_PARAMETERS for IRP_MJ_DEVICE_CONTROL and IRP_MJ_INTERNAL_DEVICE_CONTROL**](/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-device-control-and-irp-mj-internal-device-co)

[**FLT_PARAMETERS for IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-directory-control)

[**FLT_PARAMETERS for IRP_MJ_FILE_SYSTEM_CONTROL**](/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-file-system-control)

[**FLT_PARAMETERS for IRP_MJ_QUERY_EA**](/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-ea)

[**FLT_PARAMETERS for IRP_MJ_QUERY_QUOTA**](/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-quota)

[**FLT_PARAMETERS for IRP_MJ_QUERY_SECURITY**](/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-security)

[**FLT_PARAMETERS for IRP_MJ_READ**](/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-read)

[**FLT_PARAMETERS for IRP_MJ_SET_EA**](/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-ea)

[**FLT_PARAMETERS for IRP_MJ_SET_QUOTA**](/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-quota)

[**FLT_PARAMETERS for IRP_MJ_WRITE**](/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-write)

[**FltDecodeParameters**](nf-fltkernel-fltdecodeparameters.md)

[**MmGetSystemAddressForMdlSafe**](../wdm/nf-wdm-mmgetsystemaddressformdlsafe.md)

[**PFLT_POST_OPERATION_CALLBACK**](nc-fltkernel-pflt_post_operation_callback.md)

[**PFLT_PRE_OPERATION_CALLBACK**](nc-fltkernel-pflt_pre_operation_callback.md)
