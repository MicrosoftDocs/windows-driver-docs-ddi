---
UID: NF:fltkernel.FLT_IS_REISSUED_IO
tech.root: ifsk
title: FLT_IS_REISSUED_IO
ms.date: 10/11/2022
targetos: Windows
description: Learn more about the FLT_IS_REISSUED_IO macro.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: fltkernel.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - fltkernel.h
api_name:
 - FLT_IS_REISSUED_IO
f1_keywords:
 - FLT_IS_REISSUED_IO
 - fltkernel/FLT_IS_REISSUED_IO
dev_langs:
 - c++
helpviewer_keywords:
 - FLT_IS_REISSUED_IO
---

## -description

The **FLT_IS_REISSUED_IO** macro determines whether the given callback data structure represents a reissued I/O operation.

## -parameters

### -param Data

[in] Pointer to the callback data ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) structure for an I/O operation.

## -remarks

**FLT_IS_REISSUED_IO** returns TRUE if the reissued I/O operation flag is set in the callback data structure; FALSE otherwise.

The **FLT_IS_REISSUED_IO** macro checks whether the FLTFL_CALLBACK_DATA_REISSUED_IO flag is set in the **Flags** member of the [**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md) structure that the **Data** parameter points to. This flag is set by [**FltReissueSynchronousIo**](nf-fltkernel-fltreissuesynchronousio.md) when an I/O operation is reissued. This flag is valid only for IRP-based I/O operations. To determine whether an I/O operation is IRP-based, use the [**FLT_IS_IRP_OPERATION**](nf-fltkernel-flt_is_irp_operation.md) macro.

## -see-also

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FLT_IS_FASTIO_OPERATION**](nf-fltkernel-flt_is_fastio_operation.md)

[**FLT_IS_FS_FILTER_OPERATION**](nf-fltkernel-flt_is_fs_filter_operation.md)

[**FLT_IS_IRP_OPERATION**](nf-fltkernel-flt_is_irp_operation.md)

[**FLT_IS_SYSTEM_BUFFER**](nf-fltkernel-flt_is_system_buffer.md)

[**FltIsOperationSynchronous**](nf-fltkernel-fltisoperationsynchronous.md)

[**FltReissueSynchronousIo**](nf-fltkernel-fltreissuesynchronousio.md)
