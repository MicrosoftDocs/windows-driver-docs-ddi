---
UID: NF:fltkernel.FltObjectReference
title: FltObjectReference function (fltkernel.h)
description: The FltObjectReference routine adds a rundown reference to an opaque filter, instance, or volume pointer.
old-location: ifsk\fltobjectreference.htm
tech.root: ifsk
ms.assetid: ad6317bf-92fc-4e77-9993-37b7aa123a3d
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_66eccb5d-8f95-4779-b329-aaeb8b8c09b5.xml, FltObjectReference, FltObjectReference routine [Installable File System Drivers], fltkernel/FltObjectReference, ifsk.fltobjectreference
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltObjectReference
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltObjectReference function


## -description


The <b>FltObjectReference</b> routine adds a rundown reference to an opaque filter, instance, or volume pointer. 


## -parameters




### -param FltObject [in, out]

Opaque filter pointer (PFLT_FILTER), instance pointer (PFLT_INSTANCE), or volume pointer (PFLT_VOLUME). 


## -returns



<b>FltObjectReference</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

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
The minifilter driver, instance, or volume is being torn down. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



Adding a rundown reference to an opaque filter, instance, or volume object pointer prevents the object from being freed. 

To remove a rundown reference from an opaque filter, instance, or volume pointer, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543378">FltObjectDereference</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543378">FltObjectDereference</a>
 

 

