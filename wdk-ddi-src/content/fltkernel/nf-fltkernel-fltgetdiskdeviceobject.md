---
UID: NF:fltkernel.FltGetDiskDeviceObject
title: FltGetDiskDeviceObject function (fltkernel.h)
description: The FltGetDiskDeviceObject routine returns a pointer to the disk device object associated with a given volume.
old-location: ifsk\fltgetdiskdeviceobject.htm
tech.root: ifsk
ms.date: 12/02/2020
keywords: ["FltGetDiskDeviceObject function"]
ms.keywords: FltApiRef_e_to_o_830212f4-ac53-41e1-8f66-48673bdaf9e2.xml, FltGetDiskDeviceObject, FltGetDiskDeviceObject routine [Installable File System Drivers], fltkernel/FltGetDiskDeviceObject, ifsk.fltgetdiskdeviceobject
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
 - FltGetDiskDeviceObject
 - fltkernel/FltGetDiskDeviceObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetDiskDeviceObject
---

# FltGetDiskDeviceObject function

## -description

The **FltGetDiskDeviceObject** routine returns a pointer to the disk device object associated with a given volume.

## -parameters

### -param Volume

[in] Opaque pointer for the volume. This parameter is required and cannot be **NULL**.

### -param DiskDeviceObject

[out] Pointer to a caller-allocated variable that receives the device object pointer. On any error, this parameter is not modified.

## -returns

**FltGetDiskDeviceObject** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_NO_DEVICE_OBJECT | The requested device object does not exist for the given volume. This is an error code. |

## -remarks

**FltGetDiskDeviceObject** retrieves a pointer to the storage device object for the physical disk where the volume resides. The storage device need not be an actual disk.

**FltGetDiskDeviceObject** increments the reference count on the device object pointer returned in **DiskDeviceObject**. When this pointer is no longer needed, the caller must decrement this reference count by calling [**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md). Failure to do so prevents the system from freeing or deleting the device object because of the outstanding reference. Thus every successful call to **FltGetDiskDeviceObject** must be matched by a subsequent call to **ObDereferenceObject**.

A minifilter must call **FltGetDiskDeviceObject** only in an I/O related callback. Otherwise, the fields of the device object returned may not be valid. This the case in callback routines such as [**InstanceTeardownStartCallback**](nc-fltkernel-pflt_instance_teardown_callback.md) and **InstanceTeardownCompleteCallback**.

To get a pointer to the Filter Manager's volume device object (VDO) for a given volume, call [**FltGetDeviceObject**](nf-fltkernel-fltgetdeviceobject.md).

To get an opaque volume pointer for the volume represented by a volume device object, call [**FltGetVolumeFromDeviceObject**](nf-fltkernel-fltgetvolumefromdeviceobject.md).

For more information about volume device objects, see [File System Stacks](/windows-hardware/drivers/ifs/storage-device-stacks--storage-volumes--and-file-system-stacks#file-system-stacks).

## -see-also

[**FltGetDeviceObject**](nf-fltkernel-fltgetdeviceobject.md)

[**FltGetVolumeFromDeviceObject**](nf-fltkernel-fltgetvolumefromdeviceobject.md)

[**ObDereferenceObject**](../wdm/nf-wdm-obdereferenceobject.md)

[**ObReferenceObject**](../wdm/nf-wdm-obreferenceobject.md)
