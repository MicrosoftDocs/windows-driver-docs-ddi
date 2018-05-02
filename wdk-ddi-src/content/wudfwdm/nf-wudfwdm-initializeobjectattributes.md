---
UID: NF:wudfwdm.InitializeObjectAttributes
title: InitializeObjectAttributes macro
author: windows-driver-content
description: The InitializeObjectAttributes macro initializes the opaque OBJECT_ATTRIBUTES structure, which specifies the properties of an object handle to routines that open handles.
old-location: kernel\initializeobjectattributes.htm
old-project: kernel
ms.assetid: ee89a9af-0bdf-476e-b4e3-eb60662e160d
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: InitializeObjectAttributes, InitializeObjectAttributes macro [Kernel-Mode Driver Architecture], k107_f7e00cf9-9598-4835-b51a-3df9e003587e.xml, kernel.initializeobjectattributes, wudfwdm/InitializeObjectAttributes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wudfwdm.h
req.include-header: Wdm.h, Ntddk.h, Ntdef.h
req.target-type: Desktop
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wudfwdm.h
api_name:
-	InitializeObjectAttributes
product: Windows
targetos: Windows
req.typenames: 
---

# InitializeObjectAttributes macro


## -description


The <b>InitializeObjectAttributes</b> macro initializes the opaque <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> structure, which specifies the properties of an object handle to routines that open handles.


## -parameters




### -param p

TBD


### -param n

TBD


### -param a

TBD


### -param r

TBD


### -param s

TBD






#### - Attributes [in]

Specifies one or more of the following flags:





#### OBJ_INHERIT

This handle can be inherited by child processes of the current process.



#### OBJ_PERMANENT

This flag only applies to objects that are named within the object manager. By default, such objects are deleted when all open handles to them are closed. If this flag is specified, the object is not deleted when all open handles are closed. Drivers can use <a href="https://msdn.microsoft.com/library/windows/hardware/ff566477">ZwMakeTemporaryObject</a> to delete permanent objects.



#### OBJ_EXCLUSIVE

Only a single handle can be open for this object.



#### OBJ_CASE_INSENSITIVE

If this flag is specified, a case-insensitive comparison is used when matching the <i>ObjectName</i> parameter against the names of existing objects. Otherwise, object names are compared using the default system settings.



#### OBJ_OPENIF

If this flag is specified to a routine that creates objects, and that object already exists then the routine should open that object. Otherwise, the routine creating the object returns an NTSTATUS code of STATUS_OBJECT_NAME_COLLISION.



#### OBJ_KERNEL_HANDLE

Specifies that the handle can only be accessed in kernel mode.



#### OBJ_FORCE_ACCESS_CHECK

The routine opening the handle should enforce all access checks for the object, even if the handle is being opened in kernel mode.


#### - InitializedAttributes [out]

Specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> structure to initialize.


#### - ObjectName [in]

A pointer to a <a href="https://msdn.microsoft.com/b02f29a9-1049-4e29-aac3-72bf0c70a21e">Unicode string</a> that contains name of the object for which a handle is to be opened. This must either be a fully qualified object name, or a relative path name to the object directory specified by the <i>RootDirectory</i> parameter.


#### - RootDirectory [in]

A handle to the root object directory for the path name specified in the <i>ObjectName</i> parameter. If <i>ObjectName</i> is a fully qualified object name, <i>RootDirectory</i> is <b>NULL</b>. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff566421">ZwCreateDirectoryObject</a> to obtain a handle to an object directory.


#### - SecurityDescriptor [in, optional]

Specifies a security descriptor to apply to an object when it is created. This parameter is optional. Drivers can specify <b>NULL</b> to accept the default security for the object. For more information, see the following Remarks section.


## -remarks



<b>InitializeObjectAttributes</b> initializes an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> structure that specifies the properties of an object handle to be opened. The caller can then pass a pointer to this structure to a routine that actually opens the handle. 

Driver routines that run in a process context other than that of the system process must set the OBJ_KERNEL_HANDLE flag for the <i>Attributes</i> parameter. This flag restricts the use of a handle opened for that object to processes running only in kernel mode. Otherwise, the handle can be accessed by the process in whose context the driver is running.

Note that <b>InitializeObjectAttributes</b> always sets the <b>SecurityQualityOfService</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> to <b>NULL</b>. Drivers that require a non-<b>NULL</b> value can set <b>SecurityQualityOfService</b> directly.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544560">ExCreateCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548418">IoCreateFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559932">PsCreateSystemThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566421">ZwCreateDirectoryObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566424">ZwCreateFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566477">ZwMakeTemporaryObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567011">ZwOpenFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567014">ZwOpenKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567029">ZwOpenSection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567030">ZwOpenSymbolicLinkObject</a>
 

 

