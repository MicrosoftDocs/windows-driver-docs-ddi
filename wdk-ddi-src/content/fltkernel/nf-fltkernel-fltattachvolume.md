---
UID: NF:fltkernel.FltAttachVolume
title: FltAttachVolume function
author: windows-driver-content
description: FltAttachVolume creates a new minifilter driver instance and attaches it to the given volume.
old-location: ifsk\fltattachvolume.htm
old-project: ifsk
ms.assetid: da85c8d6-a74c-4a87-88b3-fb6dc01dd0f9
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: FltAttachVolume, fltkernel/FltAttachVolume, FltApiRef_a_to_d_f4ac8b0d-55c2-45b1-8f3b-3a09bee7bb23.xml, ifsk.fltattachvolume, FltAttachVolume function [Installable File System Drivers]
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	FltMgr.lib
-	FltMgr.dll
apiname:
-	FltAttachVolume
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltAttachVolume function


## -description


<b>FltAttachVolume</b> creates a new minifilter driver instance and attaches it to the given volume. 


## -syntax


````
NTSTATUS FltAttachVolume(
  _Inout_  PFLT_FILTER      Filter,
  _Inout_  PFLT_VOLUME      Volume,
  _In_opt_ PCUNICODE_STRING InstanceName,
  _Out_    PFLT_INSTANCE    *RetInstance
);
````


## -parameters




### -param Filter [in, out]

Opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param Volume [in, out]

Opaque volume pointer for the volume that the minifilter driver instance is to be attached to. This parameter is required and cannot be <b>NULL</b>. 


### -param InstanceName [in, optional]

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure containing the instance name for the new instance. This parameter is optional and can be <b>NULL</b>. If it is <b>NULL</b>, <b>FltAttachVolume</b> attempts to read the minifilter driver's default instance name from the registry. (For more information about this parameter, see the following Remarks section.) 


### -param RetInstance [out]

Pointer to a caller-allocated variable that receives an opaque instance pointer for the newly created instance. This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>FltAttachVolume</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

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
The specified <i>Filter</i> or <i>Volume</i> is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_FILTER_NOT_READY</b></dt>
</dl>
</td>
<td width="60%">
The minifilter driver has not started filtering. For more information, see <a href="..\fltkernel\nf-fltkernel-fltstartfiltering.md">FltStartFiltering</a>. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_INSTANCE_NAME_COLLISION</b></dt>
</dl>
</td>
<td width="60%">
An instance already exists with this name on the volume specified. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltAttachVolume</b> encountered a pool allocation failure. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_COLLISION</b></dt>
</dl>
</td>
<td width="60%">
Another instance was already attached at the altitude specified in the instance attributes that were read from the registry. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



If the caller specifies a non-<b>NULL</b> value for <i>InstanceName</i>, <b>FltAttachVolume</b> reads any instance attributes specified by the minifilter driver that are stored in the registry under HKLM\CurrentControlSet\Services\<i>ServiceName</i>\Instances\InstanceName, where <i>ServiceName</i> is the minifilter driver's service name. This service name is specified in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/inf-addservice-directive">AddService directive</a> in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/inf-defaultinstall-services-section">DefaultInstall.Services section</a> of the minifilter driver's INF file. (For more information about filter driver INF files, see <a href="https://msdn.microsoft.com/c8a7fd20-8baa-449a-afa6-9692da706df4">Installing a File System Filter Driver</a>.) 

If the caller does not specify a value for <i>InstanceName</i>, <b>FltAttachVolume</b> uses the name stored in the registry under HKLM\CurrentControlSet\Services\<i>ServiceName</i>\Instances\DefaultInstance for the <i>InstanceName</i> portion of the registry path. 

The instance name specified in the <i>InstanceName</i> parameter is required to be unique across the system. 

<b>FltAttachVolume</b> returns an opaque instance pointer for the new instance in <i>*RetInstance</i>. This pointer value uniquely identifies the minifilter driver instance and remains constant as long as the instance is attached to the volume. 

<b>FltAttachVolume</b> adds a rundown reference to the opaque instance pointer returned in <i>*RetInstance</i>. When this pointer is no longer needed, the caller must release it by calling <a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>. Thus every successful call to <b>FltAttachVolume</b> must be matched by a subsequent call to <b>FltObjectDereference</b>. 

To attach a minifilter driver instance to a volume at a given altitude, call <a href="..\fltkernel\nf-fltkernel-fltattachvolumeataltitude.md">FltAttachVolumeAtAltitude</a>. 

To compare the altitudes of two minifilter driver instances attached to the same volume, call <a href="..\fltkernel\nf-fltkernel-fltcompareinstancealtitudes.md">FltCompareInstanceAltitudes</a>. 

To detach a minifilter driver instance from a volume, call <a href="..\fltkernel\nf-fltkernel-fltdetachvolume.md">FltDetachVolume</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltattachvolumeataltitude.md">FltAttachVolumeAtAltitude</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\fltkernel\nf-fltkernel-fltcompareinstancealtitudes.md">FltCompareInstanceAltitudes</a>



<a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>



<a href="..\fltkernel\nf-fltkernel-fltstartfiltering.md">FltStartFiltering</a>



<a href="..\fltkernel\nf-fltkernel-fltgetvolumeinstancefromname.md">FltGetVolumeInstanceFromName</a>



<a href="..\fltkernel\nf-fltkernel-fltdetachvolume.md">FltDetachVolume</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltAttachVolume function%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

