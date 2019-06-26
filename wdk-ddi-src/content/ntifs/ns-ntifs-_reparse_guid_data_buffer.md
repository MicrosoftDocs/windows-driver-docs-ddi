---
UID: NS:ntifs._REPARSE_GUID_DATA_BUFFER
title: _REPARSE_GUID_DATA_BUFFER (ntifs.h)
description: The REPARSE_GUID_DATA_BUFFER structure contains reparse point data for a reparse point.
old-location: ifsk\reparse_guid_data_buffer.htm
tech.root: ifsk
ms.assetid: 9acb3b65-46c7-4b29-8d7a-c5d8fcd4563d
ms.date: 04/16/2018
ms.keywords: "*PREPARSE_GUID_DATA_BUFFER, PREPARSE_GUID_DATA_BUFFER, PREPARSE_GUID_DATA_BUFFER structure pointer [Installable File System Drivers], REPARSE_GUID_DATA_BUFFER, REPARSE_GUID_DATA_BUFFER structure [Installable File System Drivers], _REPARSE_GUID_DATA_BUFFER, fileinformationstructures_d020fad8-2a4b-4fe6-a1ca-bbf7575418b5.xml, ifsk.reparse_guid_data_buffer, ntifs/PREPARSE_GUID_DATA_BUFFER, ntifs/REPARSE_GUID_DATA_BUFFER"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- REPARSE_GUID_DATA_BUFFER
product:
- Windows
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

Microsoft reparse points can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_reparse_data_buffer">REPARSE_DATA_BUFFER</a> structure instead of the REPARSE_GUID_DATA_BUFFER structure. However, third-party reparse points are required to use the REPARSE_GUID_DATA_BUFFER structure. 

Reparse point tags are assigned to third parties by Microsoft. You may request more than one reparse point for use with a file system, file system filter driver, or minifilter driver. For more information about requesting a reparse point tag from Microsoft, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=8706">Windows IFS Kit</a> website. 

Reparse point GUIDs are not assigned by Microsoft. However, you must choose one GUID to use with your assigned reparse point tag, and you must always use this GUID with the tag. To generate a GUID, you should use GUIDGen (<i>Guidgen.exe</i>), a tool that is included in the Microsoft Windows SDK. 

Minifilters can set or delete a reparse point by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-flttagfile">FltTagFile</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltuntagfile">FltUntagFile</a>. Minifilters can retrieve a reparse point by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-get-reparse-point">FSCTL_GET_REPARSE_POINT</a> control code. This code can be sent to the file system by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltfscontrolfile">FltFsControlFile</a>. 

File systems and filter drivers can retrieve, set, or delete a reparse point by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-get-reparse-point">FSCTL_GET_REPARSE_POINT</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-set-reparse-point">FSCTL_SET_REPARSE_POINT</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-delete-reparse-point">FSCTL_DELETE_REPARSE_POINT</a> control codes. These codes can be sent to the file system by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff566462">ZwFsControlFile</a>. 

For more information about reparse points and reparse point tags, see the Windows SDK documentation.  




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_file_reparse_point_information">FILE_REPARSE_POINT_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-file-system-control">FLT_PARAMETERS for IRP_MJ_FILE_SYSTEM_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-delete-reparse-point">FSCTL_DELETE_REPARSE_POINT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-get-reparse-point">FSCTL_GET_REPARSE_POINT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-set-reparse-point">FSCTL_SET_REPARSE_POINT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltfscontrolfile">FltFsControlFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-flttagfile">FltTagFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltuntagfile">FltUntagFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-file-system-control">IRP_MJ_FILE_SYSTEM_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-isreparsetagmicrosoft">IsReparseTagMicrosoft</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-isreparsetagnamesurrogate">IsReparseTagNameSurrogate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_reparse_data_buffer">REPARSE_DATA_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566462">ZwFsControlFile</a>
 

 

