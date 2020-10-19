---
UID: NF:fltkernel.FltGetVolumeFromDeviceObject
title: FltGetVolumeFromDeviceObject function (fltkernel.h)
description: The FltGetVolumeFromDeviceObject routine returns an opaque pointer for the volume represented by a volume device object (VDO).
old-location: ifsk\fltgetvolumefromdeviceobject.htm
tech.root: ifsk
ms.assetid: 49dc5866-d793-41a7-9d9e-e89eea6f2f28
ms.date: 04/16/2018
keywords: ["FltGetVolumeFromDeviceObject function"]
ms.keywords: FltApiRef_e_to_o_fcc59f13-4385-478e-ba1b-c539f13930af.xml, FltGetVolumeFromDeviceObject, FltGetVolumeFromDeviceObject routine [Installable File System Drivers], fltkernel/FltGetVolumeFromDeviceObject, ifsk.fltgetvolumefromdeviceobject
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
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltGetVolumeFromDeviceObject
 - fltkernel/FltGetVolumeFromDeviceObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetVolumeFromDeviceObject
---

# FltGetVolumeFromDeviceObject function

## -description

The **FltGetVolumeFromDeviceObject** routine returns an opaque pointer for the volume represented by a volume device object (VDO).

## -parameters

### -param Filter

[in] Opaque filter pointer for the caller. This parameter is required and cannot be **NULL**.

### -param DeviceObject

[in] Pointer to the volume device object.

### -param RetVolume

[out] Pointer to a caller-allocated variable that receives an opaque pointer for the volume. This parameter is required and cannot be **NULL**.

## -returns

**FltGetVolumeFromDeviceObject** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_DELETING_OBJECT | The volume is being torn down. This is an error code. |
| STATUS_INVALID_PARAMETER | Volume device object specified in the *DeviceObject* parameter was not a valid volume device object pointer, or no matching volume was found. This is an error code. |

## -remarks

The *DeviceObject* parameter can be a pointer to a filter or a file system volume device object (VDO). If it points to a storage device object, **FltGetVolumeFromDeviceObject** returns STATUS_INVALID_PARAMETER.

For more information about volume device objects, see [File System Stacks](/windows-hardware/drivers/ifs/storage-device-stacks--storage-volumes--and-file-system-stacks#file-system-stacks).

**FltGetVolumeFromDeviceObject** adds a rundown reference to the opaque volume pointer returned in the *RetVolume* parameter. When this pointer is no longer needed, the caller must release it by calling [**FltObjectDereference**](nf-fltkernel-fltobjectdereference.md). Thus every successful call to **FltGetVolumeFromDeviceObject** must be matched by a subsequent call to **FltObjectDereference**.

To get a pointer to the device object for a given volume, call [**FltGetDeviceObject**](nf-fltkernel-fltgetdeviceobject.md).

## -see-also

[**FltGetDeviceObject**](nf-fltkernel-fltgetdeviceobject.md)

[**FltGetDiskDeviceObject**](nf-fltkernel-fltgetdiskdeviceobject.md)

[**FltObjectDereference**](nf-fltkernel-fltobjectdereference.md)
