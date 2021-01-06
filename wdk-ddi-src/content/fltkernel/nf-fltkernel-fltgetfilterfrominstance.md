---
UID: NF:fltkernel.FltGetFilterFromInstance
title: FltGetFilterFromInstance function (fltkernel.h)
description: The FltGetFilterFromInstance routine returns an opaque filter pointer for the minifilter driver that created the given instance.
old-location: ifsk\fltgetfilterfrominstance.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltGetFilterFromInstance function"]
ms.keywords: FltApiRef_e_to_o_d03cf921-2e64-49de-9929-39650fd7d03d.xml, FltGetFilterFromInstance, FltGetFilterFromInstance routine [Installable File System Drivers], fltkernel/FltGetFilterFromInstance, ifsk.fltgetfilterfrominstance
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
 - FltGetFilterFromInstance
 - fltkernel/FltGetFilterFromInstance
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetFilterFromInstance
---

# FltGetFilterFromInstance function


## -description

The <b>FltGetFilterFromInstance</b> routine returns an opaque filter pointer for the minifilter driver that created the given instance.

## -parameters

### -param Instance 

[in]
Opaque instance pointer for the instance.

### -param RetFilter 

[out]
Pointer to a caller-allocated variable that receives an opaque filter pointer for the minifilter driver. This parameter is required and cannot be <b>NULL</b>.

## -returns

<b>FltGetFilterFromInstance</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

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
The minifilter driver is being torn down. This is an error code. 

</td>
</tr>
</table>

## -remarks

<b>FltGetFilterFromInstance</b> adds a rundown reference to the opaque filter pointer returned in the <i>RetFilter</i> parameter. When this pointer is no longer needed, the caller must release it by calling <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltobjectdereference">FltObjectDereference</a>. Thus every successful call to <b>FltGetFilterFromInstance</b> must be matched by a subsequent call to <b>FltObjectDereference</b>. 

To get an opaque volume pointer for the volume to which a given minifilter driver instance is attached, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetvolumefrominstance">FltGetVolumeFromInstance</a>. 

To enumerate all instances of a given minifilter driver, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumerateinstanceinformationbyfilter">FltEnumerateInstanceInformationByFilter</a>. 

To enumerate instances of all minifilter drivers on all volumes, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumerateinstances">FltEnumerateInstances</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumerateinstanceinformationbyfilter">FltEnumerateInstanceInformationByFilter</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltenumerateinstances">FltEnumerateInstances</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetvolumefrominstance">FltGetVolumeFromInstance</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltobjectdereference">FltObjectDereference</a>
