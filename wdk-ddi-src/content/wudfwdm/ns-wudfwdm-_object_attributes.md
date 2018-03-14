---
UID: NS:wudfwdm._OBJECT_ATTRIBUTES
title: "_OBJECT_ATTRIBUTES"
author: windows-driver-content
description: The OBJECT_ATTRIBUTES structure specifies attributes that can be applied to objects or object handles by routines that create objects and/or return handles to objects.
old-location: kernel\object_attributes.htm
old-project: kernel
ms.assetid: 08f5a141-abce-4890-867c-5fe8c4239905
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*POBJECT_ATTRIBUTES, OBJECT_ATTRIBUTES, OBJECT_ATTRIBUTES structure [Kernel-Mode Driver Architecture], POBJECT_ATTRIBUTES, POBJECT_ATTRIBUTES structure pointer [Kernel-Mode Driver Architecture], _OBJECT_ATTRIBUTES, kernel.object_attributes, kstruct_c_62b87332-0ef4-4c45-8c4f-0fc12d18582b.xml, wudfwdm/OBJECT_ATTRIBUTES, wudfwdm/POBJECT_ATTRIBUTES"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wudfwdm.h
req.include-header: D3dkmthk.h, Ntdef.h, Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wudfwdm.h
api_name:
-	OBJECT_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: OBJECT_ATTRIBUTES
req.product: Windows 10 or later.
---

# _OBJECT_ATTRIBUTES structure


## -description


The <b>OBJECT_ATTRIBUTES</b> structure specifies attributes that can be applied to objects or object handles by routines that create objects and/or return handles to objects.


## -syntax


````
typedef struct _OBJECT_ATTRIBUTES {
  ULONG           Length;
  HANDLE          RootDirectory;
  PUNICODE_STRING ObjectName;
  ULONG           Attributes;
  PVOID           SecurityDescriptor;
  PVOID           SecurityQualityOfService;
}  OBJECT_ATTRIBUTES, *POBJECT_ATTRIBUTES;
````


## -struct-fields




### -field Length

The number of bytes of data contained in this structure. The <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> macro sets this member to <b>sizeof</b>(<b>OBJECT_ATTRIBUTES</b>).


### -field RootDirectory

Optional handle to the root object directory for the path name specified by the <b>ObjectName</b> member. If <b>RootDirectory</b> is <b>NULL</b>, <b>ObjectName</b> must point to a fully qualified object name that includes the full path to the target object. If <b>RootDirectory</b> is non-<b>NULL</b>, <b>ObjectName</b> specifies an object name relative to the <b>RootDirectory</b> directory. The <b>RootDirectory</b> handle can refer to a file system directory or an object directory in the object manager namespace.


### -field ObjectName

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">Unicode string</a> that contains the name of the object for which a handle is to be opened. This must either be a fully qualified object name, or a relative path name to the directory specified by the <b>RootDirectory</b> member.


### -field Attributes

Bitmask of flags that specify object handle attributes. This member can contain one or more of the flags in the following table.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
OBJ_INHERIT 

</td>
<td>
This handle can be inherited by child processes of the current process.

</td>
</tr>
<tr>
<td>
OBJ_PERMANENT

</td>
<td>
This flag only applies to objects that are named within the object manager. By default, such objects are deleted when all open handles to them are closed. If this flag is specified, the object is not deleted when all open handles are closed. Drivers can use the <a href="..\wdm\nf-wdm-zwmaketemporaryobject.md">ZwMakeTemporaryObject</a> routine to make a permanent object non-permanent.

</td>
</tr>
<tr>
<td>
OBJ_EXCLUSIVE 

</td>
<td>
If this flag is set and the <b>OBJECT_ATTRIBUTES</b> structure is passed to a routine that creates an object, the object can be accessed exclusively. That is, once a process opens such a handle to the object, no other processes can open handles to this object.

If this flag is set and the <b>OBJECT_ATTRIBUTES</b> structure is passed to a routine that creates an object handle, the caller is requesting exclusive access to the object for the process context that the handle was created in. This request can be granted only if the OBJ_EXCLUSIVE flag was set when the object was created.

</td>
</tr>
<tr>
<td>
OBJ_CASE_INSENSITIVE 

</td>
<td>
If this flag is specified, a case-insensitive comparison is used when matching the name pointed to by the <b>ObjectName</b> member against the names of existing objects. Otherwise, object names are compared using the default system settings.

</td>
</tr>
<tr>
<td>
OBJ_OPENIF 

</td>
<td>
If this flag is specified, by using the object handle, to a routine that creates objects and if that object already exists, the routine should open that object. Otherwise, the routine creating the object returns an NTSTATUS code of STATUS_OBJECT_NAME_COLLISION.

</td>
</tr>
<tr>
<td>
OBJ_OPENLINK 

</td>
<td>
If an object handle, with this flag set, is passed to a routine that opens objects and if the object is a symbolic link object, the routine should open the symbolic link object itself, rather than the object that the symbolic link refers to (which is the default behavior).

</td>
</tr>
<tr>
<td>
OBJ_KERNEL_HANDLE 

</td>
<td>
The handle is created in system process context and can only be accessed from kernel mode.

</td>
</tr>
<tr>
<td>
OBJ_FORCE_ACCESS_CHECK

</td>
<td>
The routine that opens the handle should enforce all access checks for the object, even if the handle is being opened in kernel mode.

</td>
</tr>
<tr>
<td>
OBJ_VALID_ATTRIBUTES

</td>
<td>
Reserved.

</td>
</tr>
</table>
 


### -field SecurityDescriptor

Specifies a security descriptor (<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>) for the object when the object is created. If this member is <b>NULL</b>, the object will receive default security settings.


### -field SecurityQualityOfService

Optional quality of service to be applied to the object when it is created. Used to indicate the security impersonation level and context tracking mode (dynamic or static). Currently, the <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> macro sets this member to <b>NULL</b>.


## -remarks



Use the <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> macro to initialize the members of the <b>OBJECT_ATTRIBUTES</b> structure. Note that <b>InitializeObjectAttributes</b> initializes the <b>SecurityQualityOfService</b> member to <b>NULL</b>. If you must specify a non-<b>NULL</b> value, set the <b>SecurityQualityOfService</b> member after initialization.

To apply the attributes contained in this structure to an object or object handle, pass a pointer to this structure to a routine that accesses objects or returns object handles, such as <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a> or <a href="..\wdm\nf-wdm-zwcreatedirectoryobject.md">ZwCreateDirectoryObject</a>.

All members of this structure are read-only. If a member of this structure is a pointer, the object that this member points to is read-only as well. Read-only members and objects can be used to acquire relevant information but must not be modified. To set the members of this structure, use the <b>InitializeObjectAttributes</b> macro.

Driver routines that run in a process context other than that of the system process must set the OBJ_KERNEL_HANDLE flag for the <b>Attributes</b> member (by using the <b>InitializeObjectAttributes</b> macro). This restricts the use of a handle opened for that object to processes running only in kernel mode. Otherwise, the handle can be accessed by the process in whose context the driver is running.




## -see-also

<a href="..\wdm\nf-wdm-iocreatefile.md">IoCreateFile</a>



<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatefileex.md">FltCreateFileEx</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatefile.md">FltCreateFile</a>



<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>



<a href="..\ntddk\nf-ntddk-iocreatefilespecifydeviceobjecthint.md">IoCreateFileSpecifyDeviceObjectHint</a>



<a href="..\wdm\nf-wdm-zwcreatedirectoryobject.md">ZwCreateDirectoryObject</a>



<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatecommunicationport.md">FltCreateCommunicationPort</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20OBJECT_ATTRIBUTES structure%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

