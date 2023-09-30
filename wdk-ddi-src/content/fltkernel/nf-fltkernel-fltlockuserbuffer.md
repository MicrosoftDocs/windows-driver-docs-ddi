---
UID: NF:fltkernel.FltLockUserBuffer
title: FltLockUserBuffer function (fltkernel.h)
description: Learn more about the FltLockUserBuffer function.
tech.root: ifsk
ms.date: 09/29/2023
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

Pointer to the [**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md) callback data structure for the I/O operation.

## -returns

**FltLockUserBuffer** returns STATUS_SUCCESS if it successfully locks the user buffer (or if the buffer was already locked by a previous call to **FltLockUserBuffer**.) Otherwise, it returns an appropriate NTSTATUS value, such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_INSUFFICIENT_RESOURCES | **FltLockUserBuffer** encountered a pool allocation failure. This is an error code. |
| STATUS_INVALID_PARAMETER      | An invalid parameter was encountered. For example, the I/O operation does not have an MDL parameter, or the IRP_MJ_READ or IRP_MJ_WRITE I/O operations have a minor code of IRP_MN_MDL. This is an error code. |

## -remarks

For best performance, filter drivers should not call **FltLockUserBuffer** unless absolutely necessary. The performance slowdown is not because of **FltLockUserBuffer** itself, but rather because of the performance penalty incurred by the subsequent call to [**MmGetSystemAddressForMdlSafe**](../wdm/nf-wdm-mmgetsystemaddressformdlsafe.md); see later Remarks for more information.

A minifilter driver can call **FltLockUserBuffer** to lock the user buffer for one of the following I/O operations:

* IRP_MJ_DEVICE_CONTROL
* IRP_MJ_DIRECTORY_CONTROL
* IRP_MJ_FILE_SYSTEM_CONTROL
* IRP_MJ_INTERNAL_DEVICE_CONTROL
* IRP_MJ_QUERY_EA
* IRP_MJ_QUERY_QUOTA
* IRP_MJ_QUERY_SECURITY
* IRP_MJ_READ (except with IRP_MN_MDL)
* IRP_MJ_SET_EA
* IRP_MJ_SET_QUOTA
* IRP_MJ_WRITE (except with IRP_MN_MDL)

**FltLockUserBuffer** determines the appropriate access method (IoReadAccess, IoWriteAccess, or IoModifyAccess) to apply for the locked buffer based on the type of I/O operation.

**FltLockUserBuffer** sets the **MdlAddress** (or **OutputMdlAddress**) member in the callback data parameter structure ([**FLT_PARAMETERS**](ns-fltkernel-_flt_parameters.md)) to point to the MDL for the locked pages. If there is no MDL, **FltLockUserBuffer** allocates one. (Note that FltMgr cannot generate an MDL before the file system does, which is why **FltLockUserBuffer** returns STATUS_INVALID_PARAMETER for IRP_MJ_READ or IRP_MJ_WRITE with IRP_MN_MDL).

If the callback data parameter structure contains a system buffer (**Irp->AssociatedIrp.SystemBuffer**) and does not contain a user buffer (**Irp->UserBuffer**), **FltLockUserBuffer** locks the system buffer. If there is no MDL for the system buffer, **FltLockUserBuffer** allocates one.

If the callback data parameter structure contains a user buffer, **FltLockUserBuffer** [probes and locks](../wdm/nf-wdm-mmprobeandlockpages.md) the user buffer.

The caller can be running in any process context. **FltLockUserBuffer** automatically locks the buffer in the correct process context.

If **FltLockUserBuffer** is called from a pre-operation callback routine ([**PFLT_PRE_OPERATION_CALLBACK**](nc-fltkernel-pflt_pre_operation_callback.md)) and it allocates an MDL, **FltLockUserBuffer** sets the FLTFL_CALLBACK_DATA_DIRTY flag in the callback data structure ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) so that the I/O system frees the MDL when the I/O operation is completed.

To conserve system page table entries (PTEs), **FltLockUserBuffer** doesn't map the locked pages. After calling **FltLockUserBuffer**, the caller must call [**MmGetSystemAddressForMdlSafe**](../wdm/nf-wdm-mmgetsystemaddressformdlsafe.md), passing the **MdlAddress** (or **OutputMdlAddress**) member in the callback data parameter structure as the value of the **Mdl** parameter, to get a system buffer that represents this memory.

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

[**MmProbeAndLockPages**](../wdm/nf-wdm-mmprobeandlockpages.md)

[**PFLT_POST_OPERATION_CALLBACK**](nc-fltkernel-pflt_post_operation_callback.md)

[**PFLT_PRE_OPERATION_CALLBACK**](nc-fltkernel-pflt_pre_operation_callback.md)
