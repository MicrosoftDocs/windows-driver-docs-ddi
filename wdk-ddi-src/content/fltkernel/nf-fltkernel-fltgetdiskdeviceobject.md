---
UID: NF:fltkernel.FltGetDiskDeviceObject
title: FltGetDiskDeviceObject function
author: windows-driver-content
description: The FltGetDiskDeviceObject routine returns a pointer to the disk device object associated with a given volume.
old-location: ifsk\fltgetdiskdeviceobject.htm
old-project: ifsk
ms.assetid: fb85aa34-5983-405b-85d3-7ebc4be49c51
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_e_to_o_830212f4-ac53-41e1-8f66-48673bdaf9e2.xml, FltGetDiskDeviceObject, FltGetDiskDeviceObject routine [Installable File System Drivers], fltkernel/FltGetDiskDeviceObject, ifsk.fltgetdiskdeviceobject
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	FltGetDiskDeviceObject
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetDiskDeviceObject function


## -description


The <b>FltGetDiskDeviceObject</b> routine returns a pointer to the disk device object associated with a given volume. 


## -syntax


````
NTSTATUS FltGetDiskDeviceObject(
  _In_  PFLT_VOLUME    Volume,
  _Out_ PDEVICE_OBJECT *DiskDeviceObject
);
````


## -parameters




### -param Volume [in]

Opaque pointer for the volume. This parameter is required and cannot be <b>NULL</b>. 


### -param DiskDeviceObject [out]

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

<b>FltGetDiskDeviceObject</b> increments the reference count on the device object pointer returned in *<i>DiskDeviceObject</i>. When this pointer is no longer needed, the caller must decrement this reference count by calling <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>. Failure to do so prevents the system from freeing or deleting the device object because of the outstanding reference. Thus every successful call to <b>FltGetDiskDeviceObject</b> must be matched by a subsequent call to <b>ObDereferenceObject</b>. 

A minifilter must call <b>FltGetDiskDeviceObject</b> only in an I/O related   callback. Otherwise, the fields of the device object returned may not be valid. This the case in callback routines such as <a href="..\fltkernel\nc-fltkernel-pflt_instance_teardown_callback.md">InstanceTeardownStartCallback</a> and <b>InstanceTeardownCompleteCallback</b>.

To get a pointer to the Filter Manager's volume device object (VDO) for a given volume, call <a href="..\fltkernel\nf-fltkernel-fltgetdeviceobject.md">FltGetDeviceObject</a>. 

To get an opaque volume pointer for the volume represented by a volume device object, call <a href="..\fltkernel\nf-fltkernel-fltgetvolumefromdeviceobject.md">FltGetVolumeFromDeviceObject</a>. 

For more information about volume device objects, see <a href="https://msdn.microsoft.com/67839ffb-fe38-42c2-8f33-89d01d796d8a">File System Stacks</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltgetvolumefromdeviceobject.md">FltGetVolumeFromDeviceObject</a>



<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>



<a href="..\fltkernel\nf-fltkernel-fltgetdeviceobject.md">FltGetDeviceObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetDiskDeviceObject routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

