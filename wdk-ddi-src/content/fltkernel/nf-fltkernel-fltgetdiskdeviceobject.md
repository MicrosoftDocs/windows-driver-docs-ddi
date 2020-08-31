---
UID: NF:fltkernel.FltGetDiskDeviceObject
title: FltGetDiskDeviceObject function (fltkernel.h)
description: The FltGetDiskDeviceObject routine returns a pointer to the disk device object associated with a given volume.
old-location: ifsk\fltgetdiskdeviceobject.htm
tech.root: ifsk
ms.assetid: fb85aa34-5983-405b-85d3-7ebc4be49c51
ms.date: 04/16/2018
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

The <b>FltGetDiskDeviceObject</b> routine returns a pointer to the disk device object associated with a given volume.

## -parameters

### -param Volume 

[in]
Opaque pointer for the volume. This parameter is required and cannot be <b>NULL</b>.

### -param DiskDeviceObject 

[out]
Pointer to a caller-allocated variable that receives the device object pointer. This parameter is required and cannot be <b>NULL</b>.

## -returns

<b>FltGetDiskDeviceObject</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_NO_DEVICE_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The requested device object does not exist for the given volume. This is an error code. 

</td>
</tr>
</table>

## -remarks

<b>FltGetDiskDeviceObject</b> retrieves a pointer to the storage device object for the physical disk where the volume resides. The storage device need not be an actual disk. 

<b>FltGetDiskDeviceObject</b> increments the reference count on the device object pointer returned in *<i>DiskDeviceObject</i>. When this pointer is no longer needed, the caller must decrement this reference count by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>. Failure to do so prevents the system from freeing or deleting the device object because of the outstanding reference. Thus every successful call to <b>FltGetDiskDeviceObject</b> must be matched by a subsequent call to <b>ObDereferenceObject</b>. 

A minifilter must call <b>FltGetDiskDeviceObject</b> only in an I/O related   callback. Otherwise, the fields of the device object returned may not be valid. This the case in callback routines such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_instance_teardown_callback">InstanceTeardownStartCallback</a> and <b>InstanceTeardownCompleteCallback</b>.

To get a pointer to the Filter Manager's volume device object (VDO) for a given volume, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetdeviceobject">FltGetDeviceObject</a>. 

To get an opaque volume pointer for the volume represented by a volume device object, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetvolumefromdeviceobject">FltGetVolumeFromDeviceObject</a>. 

For more information about volume device objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/file-system-stacks">File System Stacks</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetdeviceobject">FltGetDeviceObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetvolumefromdeviceobject">FltGetVolumeFromDeviceObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>

