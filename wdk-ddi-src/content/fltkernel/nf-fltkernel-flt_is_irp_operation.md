---
UID: NF:fltkernel.FLT_IS_IRP_OPERATION
tech.root: ifsk
title: FLT_IS_IRP_OPERATION
ms.date: 10/11/2022
targetos: Windows
description: Learn more about the FLT_IS_IRP_OPERATION macro.
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
 - FLT_IS_IRP_OPERATION
f1_keywords:
 - FLT_IS_IRP_OPERATION
 - fltkernel/FLT_IS_IRP_OPERATION
dev_langs:
 - c++
helpviewer_keywords:
 - FLT_IS_IRP_OPERATION
---

## -description

The **FLT_IS_IRP_OPERATION** macro determines whether the given callback data structure represents an I/O request packet (IRP)-based I/O operation.

## -parameters

### -param Data

[in] A pointer to a callback data ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) structure.

## -remarks

**FLT_IS_IRP_OPERATION** returns a nonzero value if the IRP operation flag is set in the callback data structure. Otherwise, it returns zero.

The **FLT_IS_IRP_OPERATION** macro checks whether the **FLTFL_CALLBACK_DATA_IRP_OPERATION** bit is set in the **Flags** member of the [**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md) structure that the **Data** parameter points to. Thus, the return type of **FLT_IS_IRP_OPERATION** is of the same type as the **Flags** member.

## -see-also

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FLT_IS_FASTIO_OPERATION**](nf-fltkernel-flt_is_fastio_operation.md)

[**FLT_IS_FS_FILTER_OPERATION**](nf-fltkernel-flt_is_fs_filter_operation.md)

[**FLT_IS_REISSUED_IO**](nf-fltkernel-flt_is_reissued_io.md)

[**FLT_IS_SYSTEM_BUFFER**](nf-fltkernel-flt_is_system_buffer.md)
