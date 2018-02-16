---
UID: NF:fltkernel.FltObjectReference
title: FltObjectReference function
author: windows-driver-content
description: The FltObjectReference routine adds a rundown reference to an opaque filter, instance, or volume pointer.
old-location: ifsk\fltobjectreference.htm
old-project: ifsk
ms.assetid: ad6317bf-92fc-4e77-9993-37b7aa123a3d
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: FltObjectReference, ifsk.fltobjectreference, fltkernel/FltObjectReference, FltApiRef_e_to_o_66eccb5d-8f95-4779-b329-aaeb8b8c09b5.xml, FltObjectReference routine [Installable File System Drivers]
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltObjectReference
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltObjectReference function


## -description


The <b>FltObjectReference</b> routine adds a rundown reference to an opaque filter, instance, or volume pointer. 


## -syntax


````
NTSTATUS FltObjectReference(
  _Inout_ PVOID FltObject
);
````


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

To remove a rundown reference from an opaque filter, instance, or volume pointer, call <a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltObjectReference routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

