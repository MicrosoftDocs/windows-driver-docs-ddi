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

The <b>FltGetVolumeFromDeviceObject</b> routine returns an opaque pointer for the volume represented by a volume device object (VDO).

## -parameters

### -param Filter 

[in]
Opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>.

### -param DeviceObject 

[in]
Pointer to the volume device object.

### -param RetVolume 

[out]
Pointer to a caller-allocated variable that receives an opaque pointer for the volume. This parameter is required and cannot be <b>NULL</b>.

## -returns

<b>FltGetVolumeFromDeviceObject</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The volume is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Volume device object specified in the <i>DeviceObject</i> parameter was not a valid volume device object pointer, or no matching volume was found. This is an error code. 

</td>
</tr>
</table>

## -remarks

The <i>DeviceObject</i> parameter can be a pointer to a filter or a file system volume device object (VDO). If it points to a storage device object, <b>FltGetVolumeFromDeviceObject</b> returns STATUS_INVALID_PARAMETER. 

For more information about volume device objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/file-system-stacks">File System Stacks</a>. 

<b>FltGetVolumeFromDeviceObject</b> adds a rundown reference to the opaque volume pointer returned in the <i>RetVolume</i> parameter. When this pointer is no longer needed, the caller must release it by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltobjectdereference">FltObjectDereference</a>. Thus every successful call to <b>FltGetVolumeFromDeviceObject</b> must be matched by a subsequent call to <b>FltObjectDereference</b>. 

To get a pointer to the device object for a given volume, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetdeviceobject">FltGetDeviceObject</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetdeviceobject">FltGetDeviceObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetdiskdeviceobject">FltGetDiskDeviceObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltobjectdereference">FltObjectDereference</a>

