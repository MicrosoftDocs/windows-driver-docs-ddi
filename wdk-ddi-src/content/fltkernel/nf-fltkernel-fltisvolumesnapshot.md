---
UID: NF:fltkernel.FltIsVolumeSnapshot
title: FltIsVolumeSnapshot function (fltkernel.h)
description: The FltIsVolumeSnapshot routine determines whether a volume or minifilter driver instance is attached to a snapshot volume.
old-location: ifsk\fltisvolumesnapshot.htm
tech.root: ifsk
ms.assetid: eb35e108-577e-4897-8f8c-f3c54753c1f7
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_652c8b18-8114-460b-852f-9c6bc8ff687f.xml, FltIsVolumeSnapshot, FltIsVolumeSnapshot routine [Installable File System Drivers], fltkernel/FltIsVolumeSnapshot, ifsk.fltisvolumesnapshot
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.dll: FltMgr.sys
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- FltMgr.sys
api_name:
- FltIsVolumeSnapshot
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltIsVolumeSnapshot function


## -description


The <b>FltIsVolumeSnapshot</b> routine determines whether a volume or minifilter driver instance is attached to a snapshot volume.


## -parameters




### -param FltObject [in]

An opaque pointer to the volume or instance.


### -param IsSnapshotVolume [out]

A pointer to a caller-allocated Boolean variable that receives <b>TRUE</b> if the volume or instance is attached to a snapshot volume. Otherwise, the variable receives <b>FALSE</b>.


## -returns



<b>FltIsVolumeSnapshot</b> returns one of the following NTSTATUS values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
<b>FltIsVolumeSnapshot</b> determined whether <i>FltObject</i> is a snapshot.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
<i>FltObject </i>specifies something besides a volume or an instance. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_NO_DEVICE_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
<i>FltObject</i> does not have an associated disk device object. This can occur if <i>FltObject</i> is associated with a network drive. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltIsVolumeSnapshot</b> encountered a memory allocation failure. This is an error code.

</td>
</tr>
</table>
 




## -remarks



If the volume or instance object does not support snapshots, <b>FltIsVolumeSnapshot</b> returns STATUS_SUCCESS and <i>IsSnapshotVolume</i> is <b>FALSE</b>.



