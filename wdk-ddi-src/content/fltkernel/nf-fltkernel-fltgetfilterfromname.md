---
UID: NF:fltkernel.FltGetFilterFromName
title: FltGetFilterFromName function
author: windows-driver-content
description: The FltGetFilterFromName routine returns an opaque filter pointer for a registered minifilter driver whose name matches the value in the FilterName parameter.
old-location: ifsk\fltgetfilterfromname.htm
old-project: ifsk
ms.assetid: 95224198-e86e-4005-b50f-6775e6b8b749
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_e_to_o_f0bda010-8549-4e0d-b86a-ce200745ac5a.xml, FltGetFilterFromName, FltGetFilterFromName routine [Installable File System Drivers], fltkernel/FltGetFilterFromName, ifsk.fltgetfilterfromname
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
-	FltGetFilterFromName
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetFilterFromName function


## -description


The <b>FltGetFilterFromName</b> routine returns an opaque filter pointer for a registered minifilter driver whose name matches the value in the <i>FilterName</i> parameter. 


## -syntax


````
NTSTATUS FltGetFilterFromName(
  _In_  PCUNICODE_STRING FilterName,
  _Out_ PFLT_FILTER      *RetFilter
);
````


## -parameters




### -param FilterName [in]

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure containing the minifilter driver name. (The name comparison is case-insensitive.) 


### -param RetFilter [out]

Pointer to a caller-allocated variable that receives an opaque filter pointer for the minifilter driver whose name matches the name in the <i>FilterName</i> parameter. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>FltGetFilterFromName</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

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
A matching minifilter driver was found, but it is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_FILTER_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No matching minifilter driver was found. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



<b>FltGetFilterFromName</b> adds a rundown reference to the opaque filter pointer returned in the <i>RetFilter</i> parameter. When this pointer is no longer needed, the caller must release it by calling <a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>. Thus every successful call to <b>FltGetFilterFromName</b> must be matched by a subsequent call to <b>FltObjectDereference</b>. 

To register a minifilter driver with the Filter Manager, call <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>. 




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>



<a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetFilterFromName routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

