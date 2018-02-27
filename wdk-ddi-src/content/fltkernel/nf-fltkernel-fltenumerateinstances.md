---
UID: NF:fltkernel.FltEnumerateInstances
title: FltEnumerateInstances function
author: windows-driver-content
description: The FltEnumerateInstances routine enumerates minifilter driver instances for a given minifilter driver or volume.
old-location: ifsk\fltenumerateinstances.htm
old-project: ifsk
ms.assetid: d09b95d9-4b45-4da5-9c61-8e30ed4fa1d5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_e_to_o_3875fd52-c8b1-4d79-9f90-83297dbbb44c.xml, FltEnumerateInstances, FltEnumerateInstances routine [Installable File System Drivers], fltkernel/FltEnumerateInstances, ifsk.fltenumerateinstances
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
-	FltEnumerateInstances
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltEnumerateInstances function


## -description


The <b>FltEnumerateInstances</b> routine enumerates minifilter driver instances for a given minifilter driver or volume. 


## -syntax


````
NTSTATUS FltEnumerateInstances(
  _In_opt_ PFLT_VOLUME   Volume,
  _In_opt_ PFLT_FILTER   Filter,
  _Out_    PFLT_INSTANCE *InstanceList,
  _In_     ULONG         InstanceListSize,
  _Out_    PULONG        NumberInstancesReturned
);
````


## -parameters




### -param Volume [in, optional]

Opaque pointer for the volume for which the caller wants to enumerate minifilter driver instances. If <b>NULL</b>, instances for all volumes are enumerated. Must be non-<b>NULL</b> if <i>Filter</i> is <b>NULL</b>. 


### -param Filter [in, optional]

Opaque filter pointer for the minifilter driver whose instances are to be enumerated. If <b>NULL</b>, instances for all minifilter drivers are enumerated. Must be non-<b>NULL</b> if <i>Volume</i> is <b>NULL</b>. 


### -param InstanceList [out]

Pointer to a caller-allocated buffer that receives an array of opaque instance pointers. 


### -param InstanceListSize [in]

Number of opaque instance pointers that the buffer that <i>InstanceList</i> points to can hold. 


### -param NumberInstancesReturned [out]

Pointer to a caller-allocated variable that receives the number of opaque instance pointers returned in the array that <i>InstanceList </i>points to. If <i>InstanceListSize</i> is too small, <b>FltEnumerateInstances</b> returns STATUS_BUFFER_TOO_SMALL and sets <i>NumberInstancesReturned</i> to point to the number of matching instances found. 


## -returns



<b>FltEnumerateInstances</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer that the <i>InstanceList</i> parameter points to is not large enough to store the requested information. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
<i>Volume</i> and <i>Filter</i> cannot both be <b>NULL</b>. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



Because the minifilter driver instances in the instance list can change at any time, two calls to <b>FltEnumerateInstances</b> with the same <i>Volume</i> and <i>Filter</i> values are not guaranteed to return the same result. 

<b>FltEnumerateInstances</b> adds a rundown reference to each of the opaque instance pointers returned in the array that the <i>InstanceList </i>parameter points to. When these pointers are no longer needed, the caller must release them by calling <a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a> on each one. Thus every successful call to <b>FltEnumerateInstances</b> must be matched by a subsequent call to <b>FltObjectDereference</b> for each returned instance pointer. 

To enumerate all registered minifilter drivers, call <a href="..\fltkernel\nf-fltkernel-fltenumeratefilters.md">FltEnumerateFilters</a>. 

To enumerate all volumes that are known to the Filter Manager, call <a href="..\fltkernel\nf-fltkernel-fltenumeratevolumes.md">FltEnumerateVolumes</a>. 

To list filter information for all registered minifilter drivers, call <a href="..\fltkernel\nf-fltkernel-fltenumeratefilterinformation.md">FltEnumerateFilterInformation</a>. 

To get filter information for a given minifilter driver, call <a href="..\fltkernel\nf-fltkernel-fltgetfilterinformation.md">FltGetFilterInformation</a>. 

To enumerate all instances of a given minifilter driver, call <a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyfilter.md">FltEnumerateInstanceInformationByFilter</a>. 

To enumerate all minifilter driver instances on a given volume, call <a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyvolume.md">FltEnumerateInstanceInformationByVolume</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltenumeratefilterinformation.md">FltEnumerateFilterInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyfilter.md">FltEnumerateInstanceInformationByFilter</a>



<a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>



<a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyvolume.md">FltEnumerateInstanceInformationByVolume</a>



<a href="..\fltkernel\nf-fltkernel-fltenumeratevolumes.md">FltEnumerateVolumes</a>



<a href="..\fltkernel\nf-fltkernel-fltenumeratefilters.md">FltEnumerateFilters</a>



<a href="..\fltkernel\nf-fltkernel-fltgetfilterinformation.md">FltGetFilterInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltEnumerateInstances routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

