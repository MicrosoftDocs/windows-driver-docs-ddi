---
UID: NS:ntifs._FILE_OBJECTID_INFORMATION
title: "_FILE_OBJECTID_INFORMATION"
author: windows-driver-content
description: The FILE_OBJECTID_INFORMATION structure is used to query for object ID information for the files in a directory on an NTFS volume.
old-location: ifsk\file_objectid_information.htm
tech.root: ifsk
ms.assetid: bbbaf48b-78c3-4a4b-801b-2fe3c0112a68
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PFILE_OBJECTID_INFORMATION, FILE_OBJECTID_INFORMATION, FILE_OBJECTID_INFORMATION structure [Installable File System Drivers], PFILE_OBJECTID_INFORMATION, PFILE_OBJECTID_INFORMATION structure pointer [Installable File System Drivers], _FILE_OBJECTID_INFORMATION, fileinformationstructures_330b72bc-0a91-45d2-b4c9-04d065e0545e.xml, ifsk.file_objectid_information, ntifs/FILE_OBJECTID_INFORMATION, ntifs/PFILE_OBJECTID_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available on Microsoft Windows 2000 and later.
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
-	ntifs.h
api_name:
-	FILE_OBJECTID_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILE_OBJECTID_INFORMATION, *PFILE_OBJECTID_INFORMATION
---

# _FILE_OBJECTID_INFORMATION structure


## -description


The FILE_OBJECTID_INFORMATION structure is used to query for object ID information for the files in a directory on an NTFS volume. 


## -struct-fields




### -field FileReference

The 8-byte file reference number for the file. NTFS generates this number and assigns it to the file automatically when the file is created. 


### -field ObjectId

The 16-byte file object ID for the file. NTFS generates this number and assigns it to the file at the request of a driver or application. File object IDs are guaranteed to be unique only within the volume where the file resides. 


### -field DUMMYUNIONNAME

 


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME

 


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.BirthVolumeId

 


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.BirthObjectId

 


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.DomainId

 


### -field DUMMYUNIONNAME.ExtendedInfo

User-provided data. You can use it to contain the <b>BirthVolumeID</b>, <b>BirthObjectID</b>, and <b>DomainID</b> members, or you can define a different data structure. 


#### - ( unnamed struct )

 



#### BirthVolumeId

The object identifier of the volume on which the file resided when the object identifier was created, or zero if the volume had no object identifier at that time. After copy operations, move operations, or other file operations, this may not be the same as the object identifier of the volume on which the object currently resides. 



#### BirthObjectId

The object identifier of the file at the time it was created. After copy operations, move operations, or other file operations, this may not be the same as the current value of the <b>ObjectId</b> member. 



#### DomainId

Reserved; must be zero. 


## -remarks



This information can be queried in either of the following ways: 

<ul>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff567047">ZwQueryDirectoryFile</a>, passing FileObjectIdInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_OBJECTID_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

</li>
<li>
Create an IRP with major function code IRP_MJ_DIRECTORY_CONTROL and minor function code IRP_MN_QUERY_DIRECTORY. 

</li>
</ul>
No special access rights are required to query for this information. 

Support for file reference numbers and file object IDs is file system-specific. File object IDs are supported only on NTFS volumes on Microsoft Windows 2000 and later. NTFS allows files to be opened by object ID as well as by file reference number. 

File system filter drivers that use file object IDs should be tested for interoperability with DFS, the Replicator service, and the Distributed Link Tracking service, all of which use and manipulate file object IDs. 

This structure must be aligned on a LONG (4-byte) boundary. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540318">FILE_INTERNAL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567047">ZwQueryDirectoryFile</a>
 

 

