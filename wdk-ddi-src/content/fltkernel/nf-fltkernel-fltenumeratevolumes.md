---
UID: NF:fltkernel.FltEnumerateVolumes
title: FltEnumerateVolumes function
author: windows-driver-content
description: The FltEnumerateVolumes routine enumerates all volumes in the system.
old-location: ifsk\fltenumeratevolumes.htm
old-project: ifsk
ms.assetid: 67038ff5-c450-460b-b158-f5d817fdc972
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , E, F, FltApiRef_e_to_o_20e817de-0825-4c5f-a831-2815c216344e.xml, FltEnumerateVolumes, FltEnumerateVolumes routine [Installable File System Drivers], V, a, e, fltkernel/FltEnumerateVolumes, ifsk.fltenumeratevolumes, l, m, n, o, r, s, t, u"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	FltMgr.lib
-	FltMgr.dll
apiname:
-	FltEnumerateVolumes
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltEnumerateVolumes function


## -description


The <b>FltEnumerateVolumes</b> routine enumerates all volumes in the system. 


## -syntax


````
NTSTATUS FltEnumerateVolumes(
  _In_  PFLT_FILTER Filter,
  _Out_ PFLT_VOLUME *VolumeList,
  _In_  ULONG       VolumeListSize,
  _Out_ PULONG      NumberVolumesReturned
);
````


## -parameters




### -param Filter [in]

Opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>.


### -param VolumeList [out]

Pointer to a caller-allocated buffer that receives an array of opaque volume pointers. This parameter is optional and can be <b>NULL</b> if <i>VolumeListSize</i> is zero. If <i>VolumeListSize</i> is zero on input and <i>VolumeList</i> is <b>NULL</b>, <i>NumberVolumesReturned</i> receives the number of volumes found.


### -param VolumeListSize [in]

Number of opaque filter pointers that the buffer that <i>VolumeList</i> points to can hold. This parameter is optional and can be zero. If <i>VolumeListSize</i> is zero on input and <i>VolumeList</i> is <b>NULL</b>, <i>NumberVolumesReturned</i> receives the number of volumes found.


### -param NumberVolumesReturned [out]

Pointer to a caller-allocated variable that receives the number of opaque volume pointers returned in the array that <i>VolumeList </i>points to. If <i>VolumeListSize</i> is too small and <i>VolumeList</i> is non-<b>NULL</b> on input, <b>FltEnumerateVolumes</b> returns STATUS_BUFFER_TOO_SMALL and sets <i>NumberVolumesReturned</i> to point to the number of volumes found. This parameter is required and cannot be <b>NULL</b>.


## -returns



<b>FltEnumerateVolumes</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

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
The buffer that the <i>VolumeList</i> parameter points to is not large enough to store the requested information. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



Because the contents of the filter manager's volume list can change at any time, two calls to <b>FltEnumerateVolumes</b> are not guaranteed to return the same result. 

<b>FltEnumerateVolumes</b> adds a rundown reference to each of the opaque volume pointers returned in the array that <i>VolumeList </i>points to. When these pointers are no longer needed, the caller must release them by calling <a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a> on each one. Thus every successful call to <b>FltEnumerateVolumes</b> must be matched by a subsequent call to <b>FltObjectDereference</b> for each returned volume pointer. 

To convert one or more opaque volume pointers returned by the <i>VolumeList</i> parameter into volume information, call <a href="..\fltkernel\nf-fltkernel-fltgetvolumeinformation.md">FltGetVolumeInformation</a>.

To list volume information for all volumes that are known to the filter manager, call <a href="..\fltkernel\nf-fltkernel-fltenumeratevolumeinformation.md">FltEnumerateVolumeInformation</a>. 

To enumerate all registered minifilter drivers, call <a href="..\fltkernel\nf-fltkernel-fltenumeratefilters.md">FltEnumerateFilters</a>. 

To enumerate all minifilter driver instances, call <a href="..\fltkernel\nf-fltkernel-fltenumerateinstances.md">FltEnumerateInstances</a>. 

To enumerate all minifilter driver instances on a given volume, call <a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyvolume.md">FltEnumerateInstanceInformationByVolume</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltenumerateinstances.md">FltEnumerateInstances</a>



<a href="..\fltkernel\nf-fltkernel-fltenumeratefilters.md">FltEnumerateFilters</a>



<a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyvolume.md">FltEnumerateInstanceInformationByVolume</a>



<a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>



<a href="..\fltkernel\nf-fltkernel-fltenumeratevolumeinformation.md">FltEnumerateVolumeInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltgetvolumeinformation.md">FltGetVolumeInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltEnumerateVolumes routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

