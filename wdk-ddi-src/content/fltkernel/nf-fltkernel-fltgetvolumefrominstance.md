---
UID: NF:fltkernel.FltGetVolumeFromInstance
title: FltGetVolumeFromInstance function (fltkernel.h)
description: The FltGetVolumeFromInstance routine returns an opaque pointer for the volume that a given minifilter driver instance is attached to.
old-location: ifsk\fltgetvolumefrominstance.htm
tech.root: ifsk
ms.assetid: 2c38ab6a-c583-45a5-93a5-6a5882411b6c
ms.date: 04/16/2018
keywords: ["FltGetVolumeFromInstance function"]
ms.keywords: FltApiRef_e_to_o_4e727c23-1258-41cd-a8eb-befec90c7ea9.xml, FltGetVolumeFromInstance, FltGetVolumeFromInstance routine [Installable File System Drivers], fltkernel/FltGetVolumeFromInstance, ifsk.fltgetvolumefrominstance
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
 - FltGetVolumeFromInstance
 - fltkernel/FltGetVolumeFromInstance
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetVolumeFromInstance
---

# FltGetVolumeFromInstance function


## -description

The <b>FltGetVolumeFromInstance</b> routine returns an opaque pointer for the volume that a given minifilter driver instance is attached to.

## -parameters

### -param Instance 

[in]
Opaque instance pointer for the instance.

### -param RetVolume 

[out]
Pointer to a caller-allocated variable that receives an opaque pointer for the volume. This parameter is required and cannot be <b>NULL</b>.

## -returns

<b>FltGetVolumeFromInstance</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as the following: 

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
The volume that the minifilter driver instance is attached to is being torn down. This is an error code. 

</td>
</tr>
</table>

## -remarks

<b>FltGetVolumeFromInstance</b> adds a rundown reference to the opaque volume pointer returned in the <i>RetVolume</i> parameter. When this pointer is no longer needed, the caller must release it by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltobjectdereference">FltObjectDereference</a>. Thus every successful call to <b>FltGetVolumeFromInstance</b> must be matched by a subsequent call to <b>FltObjectDereference</b>. 

To get an opaque filter pointer for the minifilter driver that created a given instance, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilterfrominstance">FltGetFilterFromInstance</a>. 

To get a pointer to the device object for a given volume, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetdeviceobject">FltGetDeviceObject</a>. 

To get detailed information about the volume that a given instance is attached to, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformation">FltQueryVolumeInformation</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetdeviceobject">FltGetDeviceObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilterfrominstance">FltGetFilterFromInstance</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltobjectdereference">FltObjectDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltqueryvolumeinformation">FltQueryVolumeInformation</a>

