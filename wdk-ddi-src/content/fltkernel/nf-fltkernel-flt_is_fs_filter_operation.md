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

The **FLT_IS_FS_FILTER_OPERATION** macro determines whether the given callback data structure represents a file system filter (FSFilter) callback operation.

## -parameters

### -param Data

[in] A pointer to a callback data ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) structure.

## -remarks

**FLT_IS_FS_FILTER_OPERATION** returns a nonzero value if the **FLTFL_CALLBACK_DATA_FS_FILTER_OPERATION** flag is set in the callback data structure. Otherwise, it returns zero.

The **FLT_IS_FS_FILTER_OPERATION** macro checks whether the **FLTFL_CALLBACK_DATA_FS_FILTER_OPERATION** bit is set in the **Flags** member of the [**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md) structure that the **Data** parameter points to. If this flag is set, the callback data structure represents one of the following file system filter (FSFilter) callback operations:

* IRP_MJ_ACQUIRE_FOR_CC_FLUSH
* IRP_MJ_ACQUIRE_FOR_MOD_WRITE
* IRP_MJ_ACQUIRE_FOR_SECTION_SYNCHRONIZATION
* IRP_MJ_RELEASE_FOR_CC_FLUSH
* IRP_MJ_RELEASE_FOR_MOD_WRITE
* IRP_MJ_RELEASE_FOR_SECTION_SYNCHRONIZATION

For information about specific FSFilter callback operations, see the reference entry for [**FsRtlRegisterFileSystemFilterCallbacks**](../ntifs/nf-ntifs-fsrtlregisterfilesystemfiltercallbacks.md). Note that in the legacy filter driver model, filters used **FsRtlRegisterFileSystemFilterCallbacks** to register callback functions for various FSFilter callback operations. However, **FsRtlRegisterFileSystemFilterCallbacks** is not used in the minifilter driver model, and minifilter drivers should never call it.

The return type of **FLT_IS_FS_FILTER_OPERATION** is of the same type as the **Flags** member of the [**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md) structure.

## -see-also

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FLT_IS_FASTIO_OPERATION**](nf-fltkernel-flt_is_fastio_operation.md)

[**FLT_IS_IRP_OPERATION**](nf-fltkernel-flt_is_irp_operation.md)

[**FLT_IS_REISSUED_IO**](nf-fltkernel-flt_is_reissued_io.md)

[**FLT_IS_SYSTEM_BUFFER**](nf-fltkernel-flt_is_system_buffer.md)

[**FsRtlRegisterFileSystemFilterCallbacks**](../ntifs/nf-ntifs-fsrtlregisterfilesystemfiltercallbacks.md)
