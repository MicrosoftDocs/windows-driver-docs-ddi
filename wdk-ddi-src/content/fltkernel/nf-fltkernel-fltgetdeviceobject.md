---
UID: NF:fltkernel.FltGetDeviceObject
title: FltGetDeviceObject function (fltkernel.h)
description: The FltGetDeviceObject routine returns a pointer to the Filter Manager's volume device object (VDO) for a given volume.
old-location: ifsk\fltgetdeviceobject.htm
tech.root: ifsk
ms.assetid: 1351efd1-1f7f-4f4b-b0ce-d9f08fba6613
ms.date: 04/16/2018
keywords: ["FltGetDeviceObject function"]
ms.keywords: FltApiRef_e_to_o_0ef7e26f-6eb6-42e3-a469-4d4fa0c8e659.xml, FltGetDeviceObject, FltGetDeviceObject routine [Installable File System Drivers], fltkernel/FltGetDeviceObject, ifsk.fltgetdeviceobject
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
req.lib: Fltmgr.lib
req.dll: Fltmgr.sys
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltGetDeviceObject
 - fltkernel/FltGetDeviceObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetDeviceObject
---

# FltGetDeviceObject function

## -description

The **FltGetDeviceObject** routine returns a pointer to the Filter Manager's volume device object (VDO) for a given volume.

## -parameters

### -param Volume

[in] Opaque pointer for the volume.

### -param DeviceObject

[out] Pointer to a caller-allocated variable that receives the volume device object pointer. This parameter is required and cannot be **NULL**.

## -returns

**FltGetDeviceObject** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_NO_DEVICE_OBJECT | The requested device object does not exist for the given volume. This is an error code. |

## -remarks

**FltGetDeviceObject** returns a pointer to the Filter Manager's volume device object (VDO) for the given volume.

For more information about volume device objects, see [File System Stacks](/windows-hardware/drivers/ifs/storage-device-stacks--storage-volumes--and-file-system-stacks#file-system-stacks).

The Filter Manager's VDO is not the same as the underlying storage driver's disk device object or the base file system's VDO. To get a pointer to the disk device object, call [**FltGetDiskDeviceObject**](nf-fltkernel-fltgetdiskdeviceobject.md) on the volume specified in the *Volume* parameter. To get a pointer to the base file system's VDO, call [**IoGetDeviceAttachmentBaseRef**](../ntifs/nf-ntifs-iogetdeviceattachmentbaseref.md) on the *RetDeviceObject* returned by **FltGetDeviceObject**.

To get an opaque pointer for the corresponding volume for a given device object, call [**FltGetVolumeFromDeviceObject**](nf-fltkernel-fltgetvolumefromdeviceobject.md).

**FltGetDeviceObject** increments the reference count on the returned device object pointer. When this pointer is no longer needed, the caller must decrement this reference count by calling [**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md). Thus every successful call to **FltGetDeviceObject** must be matched by a subsequent call to **ObDereferenceObject**.

## -see-also

[**FltGetDiskDeviceObject**](nf-fltkernel-fltgetdiskdeviceobject.md)

[**FltGetVolumeFromDeviceObject**](nf-fltkernel-fltgetvolumefromdeviceobject.md)

[**IoGetDeviceAttachmentBaseRef**](../ntifs/nf-ntifs-iogetdeviceattachmentbaseref.md)

[**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md)