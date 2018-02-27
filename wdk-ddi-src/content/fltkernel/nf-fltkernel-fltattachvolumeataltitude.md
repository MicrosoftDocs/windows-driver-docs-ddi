---
UID: NF:fltkernel.FltAttachVolumeAtAltitude
title: FltAttachVolumeAtAltitude function
author: windows-driver-content
description: FltAttachVolumeAtAltitude is a debugging support routine that attaches a minifilter driver instance to a volume at a specified altitude, overriding any settings in the minifilter driver's INF file.
old-location: ifsk\fltattachvolumeataltitude.htm
old-project: ifsk
ms.assetid: d6e6f66a-77ed-4c1c-92d5-97a806cfbd68
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_a_to_d_5a0e9e03-7d81-4894-9430-fed1c32181b6.xml, FltAttachVolumeAtAltitude, FltAttachVolumeAtAltitude routine [Installable File System Drivers], fltkernel/FltAttachVolumeAtAltitude, ifsk.fltattachvolumeataltitude
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltAttachVolumeAtAltitude
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltAttachVolumeAtAltitude function


## -description


<b>FltAttachVolumeAtAltitude</b> is a debugging support routine that attaches a minifilter driver instance to a volume at a specified altitude, overriding any settings in the minifilter driver's INF file. 


## -syntax


````
NTSTATUS FltAttachVolumeAtAltitude(
  _Inout_   PFLT_FILTER      Filter,
  _Inout_   PFLT_VOLUME      Volume,
  _In_      PCUNICODE_STRING Altitude,
  _In_opt_  PCUNICODE_STRING InstanceName,
  _Out_opt_ PFLT_INSTANCE    *RetInstance
);
````


## -parameters




### -param Filter [in, out]

Opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param Volume [in, out]

Opaque volume pointer for the volume that the minifilter driver instance is to be attached to. This parameter is required and cannot be <b>NULL</b>. 


### -param Altitude [in]

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure containing the altitude string for the instance. This parameter is required and cannot be <b>NULL</b>. (For more information about this parameter, see the following Remarks section.) 


### -param InstanceName [in, optional]

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure containing the instance name for the new instance. This parameter is optional and can be <b>NULL</b>. If it is <b>NULL</b>, <b>FltAttachVolumeAtAltitude</b> generates an instance name from the minifilter driver name and the altitude string that <i>Altitude </i>points to. The generated name is truncated, if necessary, to INSTANCE_NAME_MAX_CHARS characters. 


### -param RetInstance [out, optional]

Pointer to a caller-allocated variable that receives an opaque instance pointer for the newly created instance. This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>FltAttachVolumeAtAltitude</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

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
<dt><b>STATUS_FLT_INSTANCE_ALTITUDE_COLLISION</b></dt>
</dl>
</td>
<td width="60%">
An instance already exists at this altitude on the volume specified. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_INSTANCE_NAME_COLLISION</b></dt>
</dl>
</td>
<td width="60%">
An instance already exists with this name on the volume specified. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltAttachVolumeAtAltitude</b> encountered a pool allocation failure. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The UNICODE_STRING structure that <i>Altitude</i> points to did not contain a valid altitude string. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



A minifilter driver should only use <b>FltAttachVolumeAtAltitude</b> for debugging. It should not call this routine in a retail version of the minifilter driver. 

<b>FltAttachVolumeAtAltitude</b> is the kernel equivalent of the Win32 <a href="https://msdn.microsoft.com/library/windows/hardware/ff540448">FilterAttachAtAltitude</a> function. 

The term "altitude" refers to the position that an instance occupies (or should occupy) in the minifilter driver instance stack for a volume. The higher the altitude, the farther the instance is from the base file system in the stack. Only one instance can be attached at a given altitude on a given volume. 

Altitude is specified by an <i>altitude string</i>, which is a wide-character array containing one or more decimal digits from 0 through 9; the array can include a single decimal point. For example, "100.123456" and "03333" are valid altitude strings. 

The string "03333" represents a higher altitude than "100.123456" (Leading and trailing zeros are ignored.) In other words, an instance whose altitude is "03333" is farther from the base file system than an instance whose altitude is "100.123456". However, this comparison is only meaningful if both instances are attached to the same volume. 

The instance name specified in the <i>InstanceName</i> parameter is required to be unique across the system. 

<b>FltAttachVolumeAtAltitude</b> returns an opaque instance pointer for the new instance in <i>*RetInstance</i>. This pointer value uniquely identifies the minifilter driver instance and remains constant as long as the instance is attached to the volume. 

<b>FltAttachVolumeAtAltitude</b> adds a rundown reference to the opaque instance pointer returned in <i>*RetInstance</i>. When this pointer is no longer needed, the caller must release it by calling <a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>. Thus every successful call to <b>FltAttachVolumeAtAltitude</b> must be matched by a subsequent call to <b>FltObjectDereference</b>. 

To compare the altitudes of two minifilter driver instances attached to the same volume, call <a href="..\fltkernel\nf-fltkernel-fltcompareinstancealtitudes.md">FltCompareInstanceAltitudes</a>. 

To detach a minifilter driver instance from a volume, call <a href="..\fltkernel\nf-fltkernel-fltdetachvolume.md">FltDetachVolume</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltcompareinstancealtitudes.md">FltCompareInstanceAltitudes</a>



<a href="..\fltkernel\nf-fltkernel-fltstartfiltering.md">FltStartFiltering</a>



<a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540448">FilterAttachAtAltitude</a>



<a href="..\fltkernel\nf-fltkernel-fltattachvolume.md">FltAttachVolume</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\fltkernel\nf-fltkernel-fltgetvolumeinstancefromname.md">FltGetVolumeInstanceFromName</a>



<a href="..\fltkernel\nf-fltkernel-fltdetachvolume.md">FltDetachVolume</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltAttachVolumeAtAltitude routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

