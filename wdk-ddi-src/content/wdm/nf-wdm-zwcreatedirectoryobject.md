---
UID: NF:wdm.ZwCreateDirectoryObject
title: ZwCreateDirectoryObject function (wdm.h)
description: The ZwCreateDirectoryObject routine creates or opens an object-directory object.
old-location: kernel\zwcreatedirectoryobject.htm
tech.root: kernel
ms.assetid: 45e4a08d-9615-410a-8f78-a8157802813f
ms.date: 04/30/2018
ms.keywords: NtCreateDirectoryObject, ZwCreateDirectoryObject, ZwCreateDirectoryObject routine [Kernel-Mode Driver Architecture], k111_b1b0f371-6699-42f6-b86d-a0fb57983d9f.xml, kernel.zwcreatedirectoryobject, wdm/NtCreateDirectoryObject, wdm/ZwCreateDirectoryObject
ms.topic: function
f1_keywords:
 - "wdm/ZwCreateDirectoryObject"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwCreateDirectoryObject
- NtCreateDirectoryObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwCreateDirectoryObject function


## -description


The <b>ZwCreateDirectoryObject</b> routine creates or opens an object-directory object.


## -parameters




### -param DirectoryHandle [out]

Pointer to a HANDLE variable that receives a handle to the object directory.


### -param DesiredAccess [in]

Specifies an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that determines the requested access to the object. In addition to the access rights that are defined for all types of objects (see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>), the caller can specify one or more of the following access rights, which are specific to object directories:

<table>
<tr>
<th>ACCESS_MASK flag</th>
<th>Type of access</th>
</tr>
<tr>
<td>
DIRECTORY_QUERY

</td>
<td>
Query

</td>
</tr>
<tr>
<td>
DIRECTORY_TRAVERSE

</td>
<td>
Name lookup

</td>
</tr>
<tr>
<td>
DIRECTORY_CREATE_OBJECT

</td>
<td>
Name creation

</td>
</tr>
<tr>
<td>
DIRECTORY_CREATE_SUBDIRECTORY

</td>
<td>
Subdirectory creation

</td>
</tr>
<tr>
<td>
DIRECTORY_ALL_ACCESS

</td>
<td>
All of the preceding types

</td>
</tr>
</table>
 


### -param ObjectAttributes [in]

Pointer to an <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> structure that contains the object's attributes, which you must have already initialized by calling <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>. 


## -returns



<b>ZwCreateDirectoryObject</b> returns an NTSTATUS value. Possible return values include:




## -remarks



Once the handle pointed to by <i>DirectoryHandle</i> is no longer in use, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntclose">ZwClose</a> to close it.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/object-handles">Object Handles</a>.

The system uses object directories to organize other types of objects, such as device objects. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/object-directories">Object Directories</a>.

Note that the system does <u>not</u> use object directory objects to represent file-system directories, which are represented instead as file objects.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtCreateDirectoryObject</b>" instead of "<b>ZwCreateDirectoryObject</b>". </div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntclose">ZwClose</a>
 

 

