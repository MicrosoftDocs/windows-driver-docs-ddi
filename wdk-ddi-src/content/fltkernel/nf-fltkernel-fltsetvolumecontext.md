---
UID: NF:fltkernel.FltSetVolumeContext
title: FltSetVolumeContext function
author: windows-driver-content
description: FltSetVolumeContext sets a context for a volume.
old-location: ifsk\fltsetvolumecontext.htm
old-project: ifsk
ms.assetid: e1e8605c-b3d1-40db-bb33-fc1f7ed51617
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_p_to_z_889de924-a441-479f-9818-da016dd3feb3.xml, FltSetVolumeContext, FltSetVolumeContext function [Installable File System Drivers], fltkernel/FltSetVolumeContext, ifsk.fltsetvolumecontext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available and supported in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later operating systems. Not available nor supported in Windows 2000 SP4 and earlier operating systems.
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
-	FltSetVolumeContext
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltSetVolumeContext function


## -description


<b>FltSetVolumeContext</b> sets a context for a volume. 


## -syntax


````
NTSTATUS FltSetVolumeContext(
  _In_      PFLT_VOLUME               Volume,
  _In_      FLT_SET_CONTEXT_OPERATION Operation,
  _In_      PFLT_CONTEXT              NewContext,
  _Out_opt_ PFLT_CONTEXT              *OldContext
);
````


## -parameters




### -param Volume [in]

Opaque volume pointer for the volume. 


### -param Operation [in]

Flag specifying details of the operation to be performed. This parameter must be one of the following: 





#### FLT_SET_CONTEXT_REPLACE_IF_EXISTS

If a context is already set, replace it with <i>NewContext</i>. Otherwise, insert <i>NewContext</i> into the list of contexts for the volume. 



#### FLT_SET_CONTEXT_KEEP_IF_EXISTS

If a context is already set, return STATUS_FLT_CONTEXT_ALREADY_DEFINED. Otherwise, insert <i>NewContext</i> into the list of contexts for the volume. 


### -param NewContext [in]

Pointer to the new context to be set for the volume. This parameter is required and cannot be <b>NULL</b>. 


### -param OldContext [out, optional]

Pointer to a caller-allocated variable that receives the address of the existing volume context for <i>Instance</i>. This parameter is optional and can be <b>NULL</b>. (For more information about this parameter, see the following Remarks section.) 


## -returns



<b>FltSetVolumeContext</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_CONTEXT_ALREADY_DEFINED</b></dt>
</dl>
</td>
<td width="60%">
IF FLT_SET_CONTEXT_KEEP_IF_EXISTS was specified for <i>Operation</i>, this error code indicates that a context is already attached to the volume.  

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_CONTEXT_ALREADY_LINKED</b></dt>
</dl>
</td>
<td width="60%">
The context pointed to by the <i>NewContext</i> parameter is already linked to an object.  In other words, this error code indicates that <i>NewContext</i> is already in use due to a successful prior call of an <b>FltSet</b><i>Xxx</i><b>Context</b> routine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>Volume</i> is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the following: 

<ul>
<li>
The <i>NewContext</i> parameter does not point to a valid volume context. 

</li>
<li>
An invalid value was specified for <i>Operation</i>. 

</li>
</ul>
STATUS_INVALID_PARAMETER is an error code. 

</td>
</tr>
</table>
 




## -remarks



A minifilter driver calls <b>FltSetVolumeContext</b> to attach a context to a volume, or to remove or replace an existing volume context. A minifilter driver can attach only one context to a volume. 

A successful call to <b>FltSetVolumeContext</b> increments the reference count on <i>NewContext</i>. If <b>FltSetVolumeContext</b> fails, the reference count remains unchanged. In either case, the filter calling <b>FltSetVolumeContext</b> must call <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a> to decrement the <i>NewContext</i> object. If <b>FltSetVolumeContext</b> fails and if the <i>OldContext</i> parameter is not <b>NULL</b> and does not point to NULL_CONTEXT then <i>OldContext</i> is a referenced pointer to the context currently associated with the transaction. The filter calling <b>FltSetVolumeContext</b> must call <b>FltReleaseContext</b> for <i>OldContext</i> as well.

Note that the <i>OldContext</i> pointer returned by <b>FltSetVolumeContext</b> must also be released by calling <a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a> when it is no longer needed. For more information, see <a href="https://msdn.microsoft.com/3daa23e6-14d7-4d35-8bc8-695296cd289d">Setting Contexts</a> and <a href="https://msdn.microsoft.com/29d855cd-cca6-486b-86d9-f74810ae12c1">Releasing Contexts</a>. 

To allocate a new context, call <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 

To get a volume context, call <a href="..\fltkernel\nf-fltkernel-fltgetvolumecontext.md">FltGetVolumeContext</a>. 

To delete a volume context, call <a href="..\fltkernel\nf-fltkernel-fltdeletevolumecontext.md">FltDeleteVolumeContext</a> or <a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>. 

For more information about context reference counting, see <a href="https://msdn.microsoft.com/9ac3aedb-e057-4e19-9de5-709311072b09">Referencing Contexts</a>.




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltdeletecontext.md">FltDeleteContext</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasecontext.md">FltReleaseContext</a>



<a href="..\fltkernel\nf-fltkernel-fltgetvolumecontext.md">FltGetVolumeContext</a>



<a href="..\fltkernel\nf-fltkernel-fltdeletevolumecontext.md">FltDeleteVolumeContext</a>



<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltSetVolumeContext function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

