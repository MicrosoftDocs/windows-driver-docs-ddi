---
UID: NF:fltkernel.FltGetDeviceObject
title: FltGetDeviceObject function
author: windows-driver-content
description: The FltGetDeviceObject routine returns a pointer to the Filter Manager's volume device object (VDO) for a given volume.
old-location: ifsk\fltgetdeviceobject.htm
tech.root: ifsk
ms.assetid: 1351efd1-1f7f-4f4b-b0ce-d9f08fba6613
ms.date: 4/16/2018
ms.keywords: FltApiRef_e_to_o_0ef7e26f-6eb6-42e3-a469-4d4fa0c8e659.xml, FltGetDeviceObject, FltGetDeviceObject routine [Installable File System Drivers], fltkernel/FltGetDeviceObject, ifsk.fltgetdeviceobject
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetDeviceObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetDeviceObject function


## -description


The <b>FltGetDeviceObject</b> routine returns a pointer to the Filter Manager's volume device object (VDO) for a given volume. 


## -parameters




### -param Volume [in]

Opaque pointer for the volume. 


### -param DeviceObject [out]

Pointer to a caller-allocated variable that receives the volume device object pointer. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>FltGetDeviceObject</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

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



<b>FltGetDeviceObject</b> returns a pointer to the Filter Manager's volume device object (VDO) for the given volume. 

For more information about volume device objects, see <a href="https://msdn.microsoft.com/67839ffb-fe38-42c2-8f33-89d01d796d8a">File System Stacks</a>. 

The Filter Manager's VDO is not the same as the underlying storage driver's disk device object or the base file system's VDO. To get a pointer to the disk device object, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543013">FltGetDiskDeviceObject</a> on the volume specified in the <i>Volume</i> parameter. To get a pointer to the base file system's VDO, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548365">IoGetDeviceAttachmentBaseRef</a> on the <i>RetDeviceObject</i> returned by <b>FltGetDeviceObject</b>. 

To get an opaque pointer for the corresponding volume for a given device object, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543197">FltGetVolumeFromDeviceObject</a>. 

<b>FltGetDeviceObject</b> increments the reference count on the returned device object pointer. When this pointer is no longer needed, the caller must decrement this reference count by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>. Thus every successful call to <b>FltGetDeviceObject</b> must be matched by a subsequent call to <b>ObDereferenceObject</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543013">FltGetDiskDeviceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543197">FltGetVolumeFromDeviceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548365">IoGetDeviceAttachmentBaseRef</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>
 

 

