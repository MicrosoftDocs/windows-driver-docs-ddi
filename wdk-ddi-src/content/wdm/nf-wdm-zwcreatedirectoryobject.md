---
UID: NF:wdm.ZwCreateDirectoryObject
title: ZwCreateDirectoryObject function (wdm.h)
description: The ZwCreateDirectoryObject routine creates or opens an object-directory object.
tech.root: kernel
ms.date: 12/14/2022
keywords: ["ZwCreateDirectoryObject function"]
ms.keywords: NtCreateDirectoryObject, ZwCreateDirectoryObject, ZwCreateDirectoryObject routine [Kernel-Mode Driver Architecture], k111_b1b0f371-6699-42f6-b86d-a0fb57983d9f.xml, kernel.zwcreatedirectoryobject, wdm/NtCreateDirectoryObject, wdm/ZwCreateDirectoryObject
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwCreateDirectoryObject
 - wdm/ZwCreateDirectoryObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwCreateDirectoryObject
---

## -description

The **ZwCreateDirectoryObject** routine creates or opens an object-directory object.

## -parameters

### -param DirectoryHandle [out]

Pointer to a HANDLE variable that receives a handle to the object directory.

### -param DesiredAccess [in]

Specifies an [ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask) value that determines the requested access to the object. In addition to the access rights that are defined for all types of objects (see [ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask)), the caller can specify one or more of the following access rights, which are specific to object directories:

| ACCESS_MASK flag | Type of access |
|---|---|
| DIRECTORY_QUERY | Query |
| DIRECTORY_TRAVERSE | Name lookup |
| DIRECTORY_CREATE_OBJECT | Name creation |
| DIRECTORY_CREATE_SUBDIRECTORY | Subdirectory creation |
| DIRECTORY_ALL_ACCESS | All of the preceding types |

### -param ObjectAttributes [in]

Pointer to an [OBJECT_ATTRIBUTES](/windows/win32/api/ntdef/ns-ntdef-_object_attributes) structure that contains the object's attributes, which you must have already initialized by calling [InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes).

## -returns

**ZwCreateDirectoryObject** returns an NTSTATUS value. Possible return values include:

## -remarks

Once the handle pointed to by *DirectoryHandle* is no longer in use, the driver must call [ZwClose](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose) to close it.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see [Object Handles](/windows-hardware/drivers/kernel/object-handles).

The system uses object directories to organize other types of objects, such as device objects. For more information, see [Object Directories](/windows-hardware/drivers/kernel/object-directories).

The system does not use object directory objects to represent file-system directories, which are represented instead as file objects.

If the call to this function occurs in user mode, you should use the name "**NtCreateDirectoryObject**" instead of "**ZwCreateDirectoryObject**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[ACCESS_MASK](/windows-hardware/drivers/kernel/access-mask)

[InitializeObjectAttributes](/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[ZwClose](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose)
