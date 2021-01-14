---
UID: NS:fltkernel._FLT_OPERATION_REGISTRATION
title: _FLT_OPERATION_REGISTRATION (fltkernel.h)
description: The FLT_OPERATION_REGISTRATION structure is used to register operation callback routines.
old-location: ifsk\flt_operation_registration.htm
tech.root: ifsk
ms.date: 07/25/2019
keywords: ["FLT_OPERATION_REGISTRATION structure"]
ms.keywords: "*PFLT_OPERATION_REGISTRATION, FLT_OPERATION_REGISTRATION, FLT_OPERATION_REGISTRATION structure [Installable File System Drivers], FltSystemStructures_35ea4d15-ff73-4562-b150-d7c3e3d0823c.xml, PFLT_OPERATION_REGISTRATION, PFLT_OPERATION_REGISTRATION structure pointer [Installable File System Drivers], _FLT_OPERATION_REGISTRATION, fltkernel/FLT_OPERATION_REGISTRATION, fltkernel/PFLT_OPERATION_REGISTRATION, ifsk.flt_operation_registration"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: FLT_OPERATION_REGISTRATION, *PFLT_OPERATION_REGISTRATION
f1_keywords:
 - _FLT_OPERATION_REGISTRATION
 - fltkernel/_FLT_OPERATION_REGISTRATION
 - PFLT_OPERATION_REGISTRATION
 - fltkernel/PFLT_OPERATION_REGISTRATION
 - FLT_OPERATION_REGISTRATION
 - fltkernel/FLT_OPERATION_REGISTRATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fltkernel.h
api_name:
 - _FLT_OPERATION_REGISTRATION
 - PFLT_OPERATION_REGISTRATION
 - FLT_OPERATION_REGISTRATION
---

# _FLT_OPERATION_REGISTRATION structure


## -description

The FLT_OPERATION_REGISTRATION structure is used to register operation callback routines.

## -struct-fields

### -field MajorFunction

Major function code specifying the type of I/O operation. This member is required and cannot be **NULL**. For more information about additional operations, see [FLT_PARAMETERS](./ns-fltkernel-_flt_parameters.md).

### -field Flags

Bitmask of flags specifying when to call the preoperation ([PFLT_PRE_OPERATION_CALLBACK](./nc-fltkernel-pflt_pre_operation_callback.md)) and postoperation ([PFLT_POST_OPERATION_CALLBACK](./nc-fltkernel-pflt_post_operation_callback.md)) callback routines for cached I/O or paging I/O operations. This member is optional and can be zero.

| Flag | Description |
| ---- | ----------- |
| FLTFL_OPERATION_REGISTRATION_SKIP_PAGING_IO (0x00000001) | A minifilter sets this flag for read or write operations to specify that its preoperation and postoperation callback routines should not be called for paging I/O operations. This flag applies only to IRP-based I/O operations. It is ignored for I/O operations that are not IRP-based. |
| FLTFL_OPERATION_REGISTRATION_SKIP_CACHED_IO (0x00000002) | A minifilter sets this flag for read or write operations to specify that its preoperation and postoperation callback routines should not be called for cached I/O operations. This flag applies to fast I/O as well as IRP-based reads and writes because all fast I/O is cached. |
| FLTFL_OPERATION_REGISTRATION_SKIP_NON_DASD_IO (0x00000004) | A minifilter sets this flag so that *all* operations issued on a non-DASD volume handle will be skipped. Note that the minifilter's callback for this operation will be bypassed. |
| FLTFL_OPERATION_REGISTRATION_SKIP_NON_CACHED_NON_PAGING_IO (0x00000008) | A minifilter sets this flag so that read or write operations that are not cached nor paging will be skipped. Note that the minifilter's callback for this operation will be bypassed. This flag is relevant for IRP_MJ_READ and IRP_MJ_WRITE requests only. |

### -field PreOperation

Pointer to a [PFLT_PRE_OPERATION_CALLBACK](./nc-fltkernel-pflt_pre_operation_callback.md)-typed routine to be registered as the preoperation callback routine for this type of I/O operation. This member is optional and can be **NULL**.

### -field PostOperation

Pointer to a [PFLT_POST_OPERATION_CALLBACK](./nc-fltkernel-pflt_post_operation_callback.md)-typed routine to be registered as the postoperation callback routine for this type of I/O operation. This member is optional and can be **NULL**.

### -field Reserved1

Reserved for system use. Minifilters must set this member to **NULL**.

## -remarks

When a minifilter calls [**FltRegisterFilter**](./nf-fltkernel-fltregisterfilter.md) from its [**DriverEntry**](../wdm/nc-wdm-driver_initialize.md) routine, it can register a preoperation callback ([PFLT_PRE_OPERATION_CALLBACK](./nc-fltkernel-pflt_pre_operation_callback.md)) routine and a postoperation callback ([PFLT_POST_OPERATION_CALLBACK](./nc-fltkernel-pflt_post_operation_callback.md)) routine for each type of I/O operation that it must handle.

To register these callback routines, the minifilter creates a variable-length array of FLT_OPERATION_REGISTRATION structures and stores a pointer to the array in the **OperationRegistration** member of the [FLT_REGISTRATION](./ns-fltkernel-_flt_registration.md) structure that the minifilter passes as the *Registration* parameter of [**FltRegisterFilter**](./nf-fltkernel-fltregisterfilter.md). The last element of this array must be {IRP_MJ_OPERATION_END}.

The minifilter must create a separate FLT_OPERATION_REGISTRATION structure for each type of I/O operation that it handles. In this structure, the minifilter specifies the entry points of its callback routines in the structure's **PreOperation** and **PostOperation** members.

A minifilter can register a preoperation callback routine for a given type of I/O operation without registering a postoperation callback and vice versa.

File systems do not receive IRP_MJ_POWER or IRP_MJ_DEVICE_CHANGE requests. Minifilters cannot register preoperation or postoperation callback routines for these operations.

A minifilter cannot register a postoperation callback routine for IRP_MJ_SHUTDOWN.

A single preoperation or postoperation callback routine can be used to process more than one type of I/O operation. However, the callback routine must be registered separately for each type of I/O operation.

## -see-also

[FLT_REGISTRATION](./ns-fltkernel-_flt_registration.md)

[**FltRegisterFilter**](./nf-fltkernel-fltregisterfilter.md)

[PFLT_POST_OPERATION_CALLBACK](./nc-fltkernel-pflt_post_operation_callback.md)

[PFLT_PRE_OPERATION_CALLBACK](./nc-fltkernel-pflt_pre_operation_callback.md)

