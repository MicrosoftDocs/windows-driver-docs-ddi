---
UID: NF:fltkernel.FLT_IS_SYSTEM_BUFFER
tech.root: ifsk
title: FLT_IS_SYSTEM_BUFFER
ms.date: 10/11/2022
targetos: Windows
description: Learn more about the FLT_IS_SYSTEM_BUFFER macro.
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
 - FLT_IS_SYSTEM_BUFFER
f1_keywords:
 - FLT_IS_SYSTEM_BUFFER
 - fltkernel/FLT_IS_SYSTEM_BUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - FLT_IS_SYSTEM_BUFFER
---

## -description

The FLT\_IS\_SYSTEM\_BUFFER macro tests the system buffer flag in a callback data structure.

## -parameters

### -param Data

[in] Pointer to a callback data ([**FLT\_CALLBACK\_DATA**](ns-fltkernel-_flt_callback_data.md)) structure.

## -returns

FLT\_IS\_SYSTEM\_BUFFER returns **TRUE** if the system buffer flag is set in the callback data structure; **FALSE** otherwise.

## -remarks

The FLT\_IS\_SYSTEM\_BUFFER macro checks whether the system buffer flag (FLTFL\_CALLBACK\_DATA\_SYSTEM\_BUFFER) is set in a callback data ([**FLT\_CALLBACK\_DATA**](ns-fltkernel-_flt_callback_data.md)) structure.

The system buffer flag is set in the callback data structure for an I/O operation if the buffer for the operation is allocated from nonpaged pool. If this flag is set, minifilter drivers can assume that the buffer is already locked down and can be accessed safely.

Note that minifilter drivers must never set the system buffer flag.

## -see-also

[**FLT\_CALLBACK\_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FLT\_IS\_FASTIO\_OPERATION**](nf-fltkernel-flt_is_fastio_operation.md)

[**FLT\_IS\_FS\_FILTER\_OPERATION**](nf-fltkernel-flt_is_fs_filter_operation.md)

[**FLT\_IS\_IRP\_OPERATION**](nf-fltkernel-flt_is_irp_operation.md)

[**FLT\_IS\_REISSUED\_IO**](nf-fltkernel-flt_is_reissued_io.md)
