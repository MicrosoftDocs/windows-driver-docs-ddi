---
UID: NF:fltkernel.FLT_IS_FS_FILTER_OPERATION
tech.root: ifsk
title: FLT_IS_FS_FILTER_OPERATION
ms.date: 10/11/2022
targetos: Windows
description: Learn more about the FLT_IS_FS_FILTER_OPERATION macro.
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
 - FLT_IS_FS_FILTER_OPERATION
f1_keywords:
 - FLT_IS_FS_FILTER_OPERATION
 - fltkernel/FLT_IS_FS_FILTER_OPERATION
dev_langs:
 - c++
helpviewer_keywords:
 - FLT_IS_FS_FILTER_OPERATION
---

## -description

The FLT\_IS\_FS\_FILTER\_OPERATION macro determines whether the given callback data structure represents a file system filter (FSFilter) callback operation.

## -parameters

### -param Data

[in] A pointer to a callback data ([**FLT\_CALLBACK\_DATA**](ns-fltkernel-_flt_callback_data.md)) structure.

## -returns

FLT\_IS\_FS\_FILTER\_OPERATION returns a nonzero value if the FLTFL\_CALLBACK\_DATA\_FS\_FILTER\_OPERATION flag is set in the callback data structure. Otherwise, it returns zero.

## -remarks

The FLT\_IS\_FS\_FILTER\_OPERATION macro checks whether the FLTFL\_CALLBACK\_DATA\_FS\_FILTER\_OPERATION bit is set in the **Flags** member of the [**FLT\_CALLBACK\_DATA**](ns-fltkernel-_flt_callback_data.md) structure that the *Data* parameter points to. If this flag is set, the callback data structure represents one of the following file system filter (FSFilter) callback operations:

IRP\_MJ\_ACQUIRE\_FOR\_CC\_FLUSH

IRP\_MJ\_ACQUIRE\_FOR\_MOD\_WRITE

IRP\_MJ\_ACQUIRE\_FOR\_SECTION\_SYNCHRONIZATION

IRP\_MJ\_RELEASE\_FOR\_CC\_FLUSH

IRP\_MJ\_RELEASE\_FOR\_MOD\_WRITE

IRP\_MJ\_RELEASE\_FOR\_SECTION\_SYNCHRONIZATION

For information about specific FSFilter callback operations, see the reference entry for [**FsRtlRegisterFileSystemFilterCallbacks**](../ntifs/nf-ntifs-fsrtlregisterfilesystemfiltercallbacks.md). Note that in the legacy filter driver model, filters used **FsRtlRegisterFileSystemFilterCallbacks** to register callback functions for various FSFilter callback operations. However, **FsRtlRegisterFileSystemFilterCallbacks** is not used in the minifilter driver model, and minifilter drivers should never call it.

> [!NOTE]
> The return type of **FLT\_IS\_FS\_FILTER\_OPERATION** is of the same type as the **Flags** member of the [**FLT\_CALLBACK\_DATA**](ns-fltkernel-_flt_callback_data.md) structure.

## -see-also

[**FLT\_CALLBACK\_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FLT\_IS\_FASTIO\_OPERATION**](nf-fltkernel-flt_is_fastio_operation.md)

[**FLT\_IS\_IRP\_OPERATION**](nf-fltkernel-flt_is_irp_operation.md)

[**FLT\_IS\_REISSUED\_IO**](nf-fltkernel-flt_is_reissued_io.md)

[**FLT\_IS\_SYSTEM\_BUFFER**](nf-fltkernel-flt_is_system_buffer.md)

[**FsRtlRegisterFileSystemFilterCallbacks**](../ntifs/nf-ntifs-fsrtlregisterfilesystemfiltercallbacks.md)
