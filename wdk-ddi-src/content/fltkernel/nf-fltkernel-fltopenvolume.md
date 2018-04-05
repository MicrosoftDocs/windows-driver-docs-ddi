---
UID: NF:fltkernel.FltOpenVolume
title: FltOpenVolume function
author: windows-driver-content
description: The FltOpenVolume routine returns a handle and a file object pointer for the file system volume that a given minifilter driver instance is attached to.
old-location: ifsk\fltopenvolume.htm
old-project: ifsk
ms.assetid: 99cfa1eb-3d0f-4e27-9884-f5789ee328c3
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_e_to_o_fa9d628c-94e6-46f5-9f8f-9923c554a15f.xml, FltOpenVolume, FltOpenVolume routine [Installable File System Drivers], fltkernel/FltOpenVolume, ifsk.fltopenvolume
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP3, Windows Server 2003 SP1, and later versions of the Windows operating system.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltOpenVolume
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltOpenVolume function


## -description


The <b>FltOpenVolume</b> routine returns a handle and a file object pointer for the file system volume that a given minifilter driver instance is attached to. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the instance. This instance must be attached to a local volume. 


### -param VolumeHandle [out]

Handle for the file system volume. 


### -param VolumeFileObject [out]

Pointer to a caller-allocated variable that receives a file object pointer for the root directory of the volume. This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>FltOpenVolume</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

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
The instance or volume is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The instance is attached to a network volume. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



When the handle returned in the <i>VolumeHandle</i> parameter is no longer needed, the caller must release it by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff541863">FltClose</a>. Thus every successful call to <b>FltOpenVolume</b> must be matched by a subsequent call to <b>FltClose</b>. 

If a file object pointer is returned in the <i>VolumeFileObject</i> parameter, the caller must release it when it is no longer needed by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>. 

The instance specified by the <i>Instance</i> parameter must be attached to a local volume. If it is attached to a network volume, <b>FltOpenVolume</b> returns STATUS_INVALID_PARAMETER. 

To get a pointer to the device object for a given volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543007">FltGetDeviceObject</a>. 

To get detailed information about the volume that a given instance is attached to, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543443">FltQueryVolumeInformation</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541863">FltClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543007">FltGetDeviceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543049">FltGetFilterFromInstance</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543378">FltObjectDereference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543443">FltQueryVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a>
 

 

