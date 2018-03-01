---
UID: NF:ntifs.ZwOpenDirectoryObject
title: ZwOpenDirectoryObject function
author: windows-driver-content
description: The ZwOpenDirectoryObject routine opens an existing directory object.
old-location: kernel\zwopendirectoryobject.htm
old-project: kernel
ms.assetid: ddff6e6e-d22f-4e22-af13-aca889eee0d4
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: NtCreateDirectoryObject, ZwOpenDirectoryObject, ZwOpenDirectoryObject routine [Kernel-Mode Driver Architecture], k111_a3aca9ff-bf76-4cd0-a15d-565201c1e132.xml, kernel.zwopendirectoryobject, ntifs/NtCreateDirectoryObject, ntifs/ZwOpenDirectoryObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntdef.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ZwOpenDirectoryObject
-	NtCreateDirectoryObject
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# ZwOpenDirectoryObject function


## -description


The <b>ZwOpenDirectoryObject</b> routine opens an existing directory object. 


## -syntax


````
NTSTATUS ZwOpenDirectoryObject(
  _Out_ PHANDLE            DirectoryHandle,
  _In_  ACCESS_MASK        DesiredAccess,
  _In_  POBJECT_ATTRIBUTES ObjectAttributes
);
````


## -parameters




### -param DirectoryHandle [out]

Handle for the newly opened directory object. 


### -param DesiredAccess [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> structure specifying the requested types of access being requested for this directory object. A caller can specify one or a combination of the following.

<table>
<tr>
<th><i>DesiredAccess</i> Flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DIRECTORY_QUERY

</td>
<td>
Query access to the directory object

</td>
</tr>
<tr>
<td>
DIRECTORY_TRAVERSE

</td>
<td>
Name-lookup access to the directory object

</td>
</tr>
<tr>
<td>
DIRECTORY_CREATE_OBJECT

</td>
<td>
Name-creation access to the directory object

</td>
</tr>
<tr>
<td>
DIRECTORY_CREATE_SUBDIRECTORY

</td>
<td>
Subdirectory-creation access to the directory object

</td>
</tr>
<tr>
<td>
DIRECTORY_ALL_ACCESS

</td>
<td>
All of the preceding rights plus STANDARD_RIGHTS_REQUIRED.

</td>
</tr>
</table>
 

These requested access types are compared with the object's discretionary access-control list (<a href="..\wdm\ns-wdm-_acl.md">DACL</a>) to determine which accesses are granted or denied.


### -param ObjectAttributes [in]

Specified attributes for the directory object supplied by the caller. This parameter is initialized by calling the <b>InitializeObjectAttributes</b> macro. 


## -returns



<b>ZwOpenDirectoryObject</b> returns STATUS_SUCCESS or an appropriate error status. The most common error status codes include the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A temporary buffer required by this routine could not be allocated. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>ObjectAttributes</i> parameter was a <b>NULL</b> pointer, not a valid pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure, or some of the fields specified in the OBJECT_ATTRIBUTES structure were invalid. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The <i>ObjectAttributes</i> parameter contained an <b>ObjectName</b> field in the <b>OBJECT_ATTRIBUTES</b> structure that was invalid because an empty string was found after the OBJECT_NAME_PATH_SEPARATOR character. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The <i>ObjectAttributes</i> parameter contained an <b>ObjectName</b> field in the <b>OBJECT_ATTRIBUTES</b> structure that could not be found. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_PATH_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The <i>ObjectAttributes</i> parameter contained an <b>ObjectName</b> field in the <b>OBJECT_ATTRIBUTES</b> structure with an object path that could not be found. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_PATH_SYNTAX_BAD</b></dt>
</dl>
</td>
<td width="60%">
The <i>ObjectAttributes</i> parameter did not contain a <b>RootDirectory</b> field, but the <b>ObjectName</b> field in the <b>OBJECT_ATTRIBUTES</b> structure was an empty string or did not contain an OBJECT_NAME_PATH_SEPARATOR character. This indicates incorrect syntax for the object path. 

</td>
</tr>
</table>
 

The <b>ZwOpenDirectoryObject</b> routine throws an exception if the <i>DirectoryHandle</i> parameter is an illegal pointer.




## -remarks



<b>ZwOpenDirectoryObject</b> opens an existing directory object and returns a handle to the object. 

The <b>ZwOpenDirectoryObject</b> routine is called after the <b>InitializeObjectAttributes</b> macro is used to initialize specific attributes of the <b>OBJECT_ATTRIBUTES</b> structure for the object to be opened. 

A directory object is created using the <b>ZwCreateDirectoryObject </b>routine<b>. </b>Any handle obtained by calling <b>ZwOpenDirectoryObject</b> must eventually be released by calling <b>ZwClose</b>. 

For more information about security and access control, see the documentation on these topics in the Windows SDK. 

<div class="alert"><b>Note</b>  If the call to the <b>ZwCreateDirectoryObject </b>function occurs in user mode, you should use the name "<b>NtCreateDirectoryObject</b>" instead of "<b>ZwCreateDirectoryObject</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="..\wdm\ns-wdm-_acl.md">ACL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>



<a href="..\wdm\nf-wdm-zwcreatedirectoryobject.md">ZwCreateDirectoryObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwOpenDirectoryObject routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

