---
UID: NF:fltkernel.FltDecodeParameters
title: FltDecodeParameters function (fltkernel.h)
description: FltDecodeParameters returns pointers to the memory descriptor list (MDL) address, buffer pointer, buffer length, and desired access parameters for an I/O operation.
old-location: ifsk\fltdecodeparameters.htm
tech.root: ifsk
ms.date: 11/23/2021
keywords: ["FltDecodeParameters function"]
ms.keywords: FltApiRef_a_to_d_0e793d86-f756-4885-8b23-5f74cd50b144.xml, FltDecodeParameters, FltDecodeParameters routine [Installable File System Drivers], fltkernel/FltDecodeParameters, ifsk.fltdecodeparameters
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
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - FltDecodeParameters
 - fltkernel/FltDecodeParameters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltDecodeParameters
---

# FltDecodeParameters function

## -description

**FltDecodeParameters** returns pointers to the memory descriptor list (MDL) address, buffer pointer, buffer length, and desired access parameters for an I/O operation. This saves minifilter drivers from having a switch statement to find the position of these parameters in helper routines that access the MDL address, buffer pointer, buffer length, and desired access for multiple operation types.

## -parameters

### -param CallbackData [in]

Pointer to the callback data ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) structure for the I/O operation.

### -param MdlAddressPointer [out]

Pointer to a caller-supplied variable that receives a pointer to the **MdlAddress** (or **OutputMdlAddress**) member of the callback data parameter ([**FLT_PARAMETERS**](ns-fltkernel-_flt_parameters.md)) structure (note that this member is itself a pointer). This parameter is optional and can be **NULL**. If the I/O operation does not have an MDL field, this parameter receives **NULL**.

### -param Buffer [out]

Pointer to a caller-supplied variable that receives a pointer to the appropriate buffer member (depending on the major function code) in the callback data parameter structure (note that this member is itself a pointer).

### -param Length [out]

Pointer to a caller-supplied variable that receives a pointer to the buffer length member in the callback data parameter structure. If the operation does not have a length field, this parameter receives **NULL**.

### -param DesiredAccess [out, optional]

Pointer to a caller-supplied variable that receives the type of access that is appropriate for this type of I/O operation, one of **IoReadAccess**, **IoWriteAccess**, or **IoModifyAccess**. **IoReadAccess** means that the minifilter driver can examine the contents of the buffer but cannot change the contents in place. **IoWriteAccess** and **IoModifyAccess**, which are equivalent, mean that the minifilter driver has read and write access to the buffer.

## -returns

**FltDecodeParameters** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_INVALID_PARAMETER | The callback data ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) structure represents an I/O operation that does not have any buffer parameters. This is an error code. |

## -remarks

**FltDecodeParameters** returns pointers to the parameters for an I/O operation, rather than the parameter values, so that the caller can modify the values of the parameters if desired.

**FltDecodeParameters** can be used for fast I/O operations as well as IRP-based operations. It is not meaningful for file system filter (FSFilter) callback operations, because those operations do not have buffer parameters.

IOCTL and FSCTL operations can have one or two buffers, depending on the buffering method used. In cases where the operation has two buffers (and two length fields), **FltDecodeParameters** returns the **OutputBuffer**, **OutputBufferLength**, and/or **OutputMdlAddress** fields as appropriate.

Not all of the four parameters are returned for every I/O operation. For example, for an IRP_MJ_READ request, **FltDecodeParameters** sets the output parameters as follows.

| Parameter | Value |
| --------- | ----- |
| **MdlAddressPointer** | &(CallbackData->Iopb->Parameters.Read.MdlAddress) |
| **Buffer**            | &(CallbackData->Iopb->Parameters.Read.ReadBuffer) |
| **Length**            | &(CallbackData->Iopb->Parameters.Read.Length)     |
| **DesiredAccess**     | IoWriteAccess                                     |

## -see-also

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)

[**FLT_IS_FASTIO_OPERATION**](nf-fltkernel-flt_is_fastio_operation.md)

[**FLT_IS_FS_FILTER_OPERATION**](/previous-versions/ff544648(v=vs.85))

[**FLT_IS_IRP_OPERATION**](/previous-versions/ff544654(v=vs.85))

[**FLT_PARAMETERS**](ns-fltkernel-_flt_parameters.md)

[**FltLockUserBuffer**](nf-fltkernel-fltlockuserbuffer.md)
