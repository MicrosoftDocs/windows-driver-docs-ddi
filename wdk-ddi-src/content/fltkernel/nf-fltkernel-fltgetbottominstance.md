---
UID: NF:fltkernel.FltGetBottomInstance
title: FltGetBottomInstance function
author: windows-driver-content
description: FltGetBottomInstance returns an opaque instance pointer for the minifilter driver instance, if there is one, that is attached at the bottom of the instance stack for a given volume.
old-location: ifsk\fltgetbottominstance.htm
old-project: ifsk
ms.assetid: a5e7379a-6501-4245-92ce-0474baa33e2c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_e_to_o_14e06d93-d5c8-4154-9184-d30beef6c126.xml, FltGetBottomInstance, FltGetBottomInstance function [Installable File System Drivers], fltkernel/FltGetBottomInstance, ifsk.fltgetbottominstance
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
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetBottomInstance
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetBottomInstance function


## -description


<b>FltGetBottomInstance</b> returns an opaque instance pointer for the minifilter driver instance, if there is one, that is attached at the bottom of the instance stack for a given volume. 


## -syntax


````
NTSTATUS FltGetBottomInstance(
  _In_  PFLT_VOLUME   Volume,
  _Out_ PFLT_INSTANCE *Instance
);
````


## -parameters




### -param Volume [in]

Opaque pointer for the volume. 


### -param Instance [out]

Pointer to a caller-allocated variable that receives an opaque instance pointer for the bottom instance for this volume. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>FltGetBottomInstance</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>
</td>
<td width="60%">
No matching instance was found. This is a warning code. 

</td>
</tr>
</table>
 




## -remarks



An instance is said to be at the <i>bottom</i> of the minifilter driver instance stack if its altitude is lower than that of all other instances attached to the same volume. The term "altitude" refers to the position that an instance occupies in the minifilter driver instance stack for a volume. The higher the altitude, the farther the instance is from the base file system in the stack. Only one instance can be attached at a given altitude on a given volume. 

Altitude is specified by an <i>altitude string</i>, which is a counted Unicode string consisting of one or more decimal digits from 0 through 9, and it can include a single decimal point. For example, "100.123456" and "03333" are valid altitude strings. 

The string "03333" represents a higher altitude than "100.123456". (Leading and trailing zeros are ignored.) In other words, an instance whose altitude is "03333" is farther from the base file system than an instance whose altitude is "100.123456". However, this comparison is only meaningful if both instances are attached to the same volume. 

<b>FltGetBottomInstance</b> adds a rundown reference to the opaque instance pointer returned in *<i>Instance</i>. When this pointer is no longer needed, the caller must release it by calling <a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>. Thus every successful call to <b>FltGetBottomInstance</b> must be matched by a subsequent call to <b>FltObjectDereference</b>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltcompareinstancealtitudes.md">FltCompareInstanceAltitudes</a>



<a href="..\fltkernel\nf-fltkernel-fltattachvolumeataltitude.md">FltAttachVolumeAtAltitude</a>



<a href="..\fltkernel\nf-fltkernel-fltgetlowerinstance.md">FltGetLowerInstance</a>



<a href="..\fltkernel\nf-fltkernel-fltgetupperinstance.md">FltGetUpperInstance</a>



<a href="..\fltkernel\nf-fltkernel-fltattachvolume.md">FltAttachVolume</a>



<a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>



<a href="..\fltkernel\nf-fltkernel-fltgettopinstance.md">FltGetTopInstance</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetBottomInstance function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

