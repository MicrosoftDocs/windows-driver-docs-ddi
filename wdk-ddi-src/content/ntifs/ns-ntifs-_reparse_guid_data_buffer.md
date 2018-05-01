---
UID: NS:ntifs._REPARSE_GUID_DATA_BUFFER
title: "_REPARSE_GUID_DATA_BUFFER"
author: windows-driver-content
description: The REPARSE_GUID_DATA_BUFFER structure contains reparse point data for a reparse point.
old-location: ifsk\reparse_guid_data_buffer.htm
old-project: ifsk
ms.assetid: 9acb3b65-46c7-4b29-8d7a-c5d8fcd4563d
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PREPARSE_GUID_DATA_BUFFER, PREPARSE_GUID_DATA_BUFFER, PREPARSE_GUID_DATA_BUFFER structure pointer [Installable File System Drivers], REPARSE_GUID_DATA_BUFFER, REPARSE_GUID_DATA_BUFFER structure [Installable File System Drivers], _REPARSE_GUID_DATA_BUFFER, fileinformationstructures_d020fad8-2a4b-4fe6-a1ca-bbf7575418b5.xml, ifsk.reparse_guid_data_buffer, ntifs/PREPARSE_GUID_DATA_BUFFER, ntifs/REPARSE_GUID_DATA_BUFFER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	REPARSE_GUID_DATA_BUFFER
product: Windows
targetos: Windows
req.typenames: REPARSE_GUID_DATA_BUFFER, *PREPARSE_GUID_DATA_BUFFER
---

# _REPARSE_GUID_DATA_BUFFER structure


## -description


The REPARSE_GUID_DATA_BUFFER structure contains reparse point data for a reparse point. 


## -struct-fields




### -field ReparseTag

Reparse point tag that uniquely identifies the owner of the reparse point. (See the following <b>Remarks</b> section.) 


### -field ReparseDataLength

Size, in bytes, of the reparse data in the <b>DataBuffer</b> member. 


### -field Reserved

Reserved; do not use. 


### -field ReparseGuid

GUID that uniquely identifies the owner of the reparse point. (See the following <b>Remarks</b> section.) 


### -field GenericReparseBuffer


### -field GenericReparseBuffer.DataBuffer

User-defined data for the reparse point. The format of this data is defined by the owner of the reparse point. 


## -remarks



The REPARSE_GUID_DATA_BUFFER structure is used by all third-party file systems, filters, and minifilters, as well as some Microsoft file systems, filters, and minifilters to store data for a reparse point. Each reparse point contains one REPARSE_GUID_DATA_BUFFER structure. 

Microsoft reparse points can use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552012">REPARSE_DATA_BUFFER</a> structure instead of the REPARSE_GUID_DATA_BUFFER structure. However, third-party reparse points are required to use the REPARSE_GUID_DATA_BUFFER structure. 

Reparse point tags are assigned to third parties by Microsoft. You may request more than one reparse point for use with a file system, file system filter driver, or minifilter driver. For more information about requesting a reparse point tag from Microsoft, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=8706">Windows IFS Kit</a> website. 

Reparse point GUIDs are not assigned by Microsoft. However, you must choose one GUID to use with your assigned reparse point tag, and you must always use this GUID with the tag. To generate a GUID, you should use GUIDGen (<i>Guidgen.exe</i>), a tool that is included in the Microsoft Windows SDK. 

Minifilters can set or delete a reparse point by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544589">FltTagFile</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff544608">FltUntagFile</a>. Minifilters can retrieve a reparse point by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544836">FSCTL_GET_REPARSE_POINT</a> control code. This code can be sent to the file system by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff542988">FltFsControlFile</a>. 

File systems and filter drivers can retrieve, set, or delete a reparse point by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544836">FSCTL_GET_REPARSE_POINT</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff545568">FSCTL_SET_REPARSE_POINT</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff544828">FSCTL_DELETE_REPARSE_POINT</a> control codes. These codes can be sent to the file system by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff566462">ZwFsControlFile</a>. 

For more information about reparse points and reparse point tags, see the Windows SDK documentation.  




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540354">FILE_REPARSE_POINT_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544705">FLT_PARAMETERS for IRP_MJ_FILE_SYSTEM_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544828">FSCTL_DELETE_REPARSE_POINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544836">FSCTL_GET_REPARSE_POINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545568">FSCTL_SET_REPARSE_POINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542988">FltFsControlFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544589">FltTagFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544608">FltUntagFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550751">IRP_MJ_FILE_SYSTEM_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549452">IsReparseTagMicrosoft</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549462">IsReparseTagNameSurrogate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552012">REPARSE_DATA_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566462">ZwFsControlFile</a>
 

 

