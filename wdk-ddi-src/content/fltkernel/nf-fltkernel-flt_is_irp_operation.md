---
UID: NF:fltkernel.FLT_IS_IRP_OPERATION
tech.root: ifs
title: FLT_IS_IRP_OPERATION
ms.date: 10/07/2022
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

The FLT\_IS\_IRP\_OPERATION macro determines whether the given callback data structure represents an I/O request packet (IRP)-based I/O operation.

## -parameters

[in] A pointer to a callback data ([**FLT\_CALLBACK\_DATA**](ns-fltkernel-_flt_callback_data.md)) structure.### -param Data

## -returns

FLT\_IS\_IRP\_OPERATION returns a nonzero value if the IRP operation flag is set in the callback data structure. Otherwise, it returns zero.

## -remarks

The FLT\_IS\_IRP\_OPERATION macro checks whether the FLTFL\_CALLBACK\_DATA\_IRP\_OPERATION bit is set in the **Flags** member of the [**FLT\_CALLBACK\_DATA**](ns-fltkernel-_flt_callback_data.md) structure that the *Data* parameter points to. Thus, the return type of **FLT\_IS\_IRP\_OPERATION** is of the same type as the **Flags** member.

## -see-also

[**FLT\_CALLBACK\_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FLT\_IS\_FASTIO\_OPERATION**](nf-fltkernel-flt_is_fastio_operation.md)

[**FLT\_IS\_FS\_FILTER\_OPERATION**](nf-fltkernel-flt_is_fs_filter_operation.md)

[**FLT\_IS\_REISSUED\_IO**](nf-fltkernel-flt_is_reissued_io.md)

[**FLT\_IS\_SYSTEM\_BUFFER**](nf-fltkernel-flt_is_system_buffer.md)
