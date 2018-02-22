---
UID: NF:ntifs.ObQueryNameString
title: ObQueryNameString function
author: windows-driver-content
description: The ObQueryNameString routine supplies the name, if there is one, of a given object to which the caller has a pointer.
old-location: ifsk\obquerynamestring.htm
old-project: ifsk
ms.assetid: 3c540410-6478-4da1-8ef5-b6d21d322b32
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntifs/ObQueryNameString, ObQueryNameString, obref_3d52f727-edc5-4bea-b7c1-24a3aced1079.xml, ifsk.obquerynamestring, ObQueryNameString routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later operating systems.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "< DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ObQueryNameString
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# ObQueryNameString function


## -description


The <b>ObQueryNameString</b> routine supplies the name, if there is one, of a given object to which the caller has a pointer.


## -syntax


````
NTSTATUS ObQueryNameString(
  _In_      PVOID                    Object,
  _Out_opt_ POBJECT_NAME_INFORMATION ObjectNameInfo,
  _In_      ULONG                    Length,
  _Out_     PULONG                   ReturnLength
);
````


## -parameters




### -param Object [in]

A pointer to the object for which the name is requested. This parameter is required and cannot be <b>NULL</b>. 


### -param ObjectNameInfo [out, optional]

A pointer to a caller-allocated buffer, of the following type, that receives the object name information: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _OBJECT_NAME_INFORMATION {
  UNICODE_STRING Name;
} OBJECT_NAME_INFORMATION, *POBJECT_NAME_INFORMATION;</pre>
</td>
</tr>
</table></span></div>
This parameter is optional and can be <b>NULL</b>. If <i>ObjectNameInfo</i> is <b>NULL</b>, <i>Length</i> must be zero.


### -param Length [in]

The size, in bytes, of the buffer that is pointed to by <i>ObjectNameInfo</i>. This parameter is optional and can be zero. If <i>Length</i> is zero, <i>ReturnLength</i> receives the size, in bytes, of the buffer that is needed to hold the object name information. A reasonable size for the buffer to accommodate most object names is 1024 bytes. If <i>Length</i> is zero, <i>ObjectNameInfo</i> can be <b>NULL</b>.


### -param ReturnLength [out]

A pointer to a caller-allocated variable that receives the size, in bytes, of the returned object name information. The object name (when present) includes a NULL-terminator and all path separators "\" in the name. If <b>ObQueryNameString</b> returns <b>STATUS_INFO_LENGTH_MISMATCH</b>, it sets this parameter to the required buffer length. 


## -returns



<b>ObQueryNameString</b> returns STATUS_SUCCESS or an NTSTATUS value such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The buffer that is pointed to by <i>ObjectNameInfo</i> is too small to hold the requested object name information. <i>ReturnLength</i> points to the required buffer size. In this case, no object name information is returned. This is an error code. Be aware that if <i>Length</i> is set to zero, <b>STATUS_INFO_LENGTH_MISMATCH</b> is returned.

</td>
</tr>
</table>
 




## -remarks



If the given object is named and the object name was successfully acquired, the returned string is the name of the given object including as much of the object's full path as possible. In this case, <b>ObQueryNameString</b> sets <b>Name.Buffer</b> to the address of the NULL-terminated name of the specified object. The value of <b>Name.MaximumLength</b> is the length of the object name including the <b>NULL</b> termination. The value of <b>Name.Length</b> is length of the only the object name.

If the given object is unnamed, or if the object name was not successfully acquired, <b>ObQueryNameString</b> sets <b>Name.Buffer</b> to <b>NULL</b> and sets <b>Name.Length</b> and <b>Name.MaximumLength</b> to zero.

The storage for <i>ObjectNameInfo</i> can be allocated from paged or nonpaged pool. 




## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20ObQueryNameString routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

