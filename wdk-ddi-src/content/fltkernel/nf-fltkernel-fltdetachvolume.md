---
UID: NF:fltkernel.FltDetachVolume
title: FltDetachVolume function
author: windows-driver-content
description: FltDetachVolume detaches a minifilter driver instance from a volume.
old-location: ifsk\fltdetachvolume.htm
old-project: ifsk
ms.assetid: 889750fc-69a9-4fe6-8905-6a7edc5c04fb
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_a_to_d_2f7a4638-6f6d-4ac6-97b6-d547d64b56b6.xml, FltDetachVolume, FltDetachVolume function [Installable File System Drivers], fltkernel/FltDetachVolume, ifsk.fltdetachvolume
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
req.lib: FltMgr.lib
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltDetachVolume
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltDetachVolume function


## -description


<b>FltDetachVolume</b> detaches a minifilter driver instance from a volume. 


## -syntax


````
NTSTATUS FltDetachVolume(
  _Inout_  PFLT_FILTER      Filter,
  _Inout_  PFLT_VOLUME      Volume,
  _In_opt_ PCUNICODE_STRING InstanceName
);
````


## -parameters




### -param Filter [in, out]

Opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param Volume [in, out]

Opaque volume pointer for the volume where the instance is attached. This parameter is required and cannot be <b>NULL</b>. 


### -param InstanceName [in, optional]

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure containing the instance name for the instance to be removed. This parameter is optional and can be <b>NULL</b>. If it is <b>NULL</b>, the highest matching instance is removed. 


## -returns



<b>FltDetachVolume</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

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
<b>FltDetachVolume</b> found a matching instance, but the instance is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_INSTANCE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No matching instance was found. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



<b>FltDetachVolume</b> detaches a minifilter driver instance from a volume and tears down the instance. 

To attach a minifilter driver instance to a volume, call <a href="..\fltkernel\nf-fltkernel-fltattachvolume.md">FltAttachVolume</a> or <a href="..\fltkernel\nf-fltkernel-fltattachvolumeataltitude.md">FltAttachVolumeAtAltitude</a>. 

To compare the altitudes of two minifilter driver instances attached to the same volume, call <a href="..\fltkernel\nf-fltkernel-fltcompareinstancealtitudes.md">FltCompareInstanceAltitudes</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltattachvolume.md">FltAttachVolume</a>



<a href="..\fltkernel\nf-fltkernel-fltcompareinstancealtitudes.md">FltCompareInstanceAltitudes</a>



<a href="..\fltkernel\nf-fltkernel-fltattachvolumeataltitude.md">FltAttachVolumeAtAltitude</a>



<a href="..\fltkernel\nf-fltkernel-fltgetvolumeinstancefromname.md">FltGetVolumeInstanceFromName</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltDetachVolume function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

