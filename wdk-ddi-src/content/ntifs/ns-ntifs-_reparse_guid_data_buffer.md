---
UID: NS:ntifs._REPARSE_GUID_DATA_BUFFER
title: "_REPARSE_GUID_DATA_BUFFER"
author: windows-driver-content
description: The REPARSE_GUID_DATA_BUFFER structure contains reparse point data for a reparse point.
old-location: ifsk\reparse_guid_data_buffer.htm
old-project: ifsk
ms.assetid: 9acb3b65-46c7-4b29-8d7a-c5d8fcd4563d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: REPARSE_GUID_DATA_BUFFER, _REPARSE_GUID_DATA_BUFFER, *PREPARSE_GUID_DATA_BUFFER, ntifs/REPARSE_GUID_DATA_BUFFER, PREPARSE_GUID_DATA_BUFFER structure pointer [Installable File System Drivers], fileinformationstructures_d020fad8-2a4b-4fe6-a1ca-bbf7575418b5.xml, ntifs/PREPARSE_GUID_DATA_BUFFER, REPARSE_GUID_DATA_BUFFER structure [Installable File System Drivers], ifsk.reparse_guid_data_buffer, PREPARSE_GUID_DATA_BUFFER
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	REPARSE_GUID_DATA_BUFFER
product: Windows
targetos: Windows
req.typenames: REPARSE_GUID_DATA_BUFFER, *PREPARSE_GUID_DATA_BUFFER
---

# _REPARSE_GUID_DATA_BUFFER structure


## -description


The REPARSE_GUID_DATA_BUFFER structure contains reparse point data for a reparse point. 


## -syntax


````
typedef struct _REPARSE_GUID_DATA_BUFFER {
  ULONG  ReparseTag;
  USHORT ReparseDataLength;
  USHORT Reserved;
  GUID   ReparseGuid;
  struct {
    UCHAR DataBuffer[1];
  } GenericReparseBuffer;
} REPARSE_GUID_DATA_BUFFER, *PREPARSE_GUID_DATA_BUFFER;
````


## -struct-fields




### -field GenericReparseBuffer



### -field GenericReparseBuffer.DataBuffer

User-defined data for the reparse point. The format of this data is defined by the owner of the reparse point. 


### -field ReparseTag

Reparse point tag that uniquely identifies the owner of the reparse point. (See the following <b>Remarks</b> section.) 


### -field ReparseDataLength

Size, in bytes, of the reparse data in the <b>DataBuffer</b> member. 


### -field Reserved

Reserved; do not use. 


### -field ReparseGuid

GUID that uniquely identifies the owner of the reparse point. (See the following <b>Remarks</b> section.) 


## -remarks


The REPARSE_GUID_DATA_BUFFER structure is used by all third-party file systems, filters, and minifilters, as well as some Microsoft file systems, filters, and minifilters to store data for a reparse point. Each reparse point contains one REPARSE_GUID_DATA_BUFFER structure. 

Microsoft reparse points can use the <a href="..\ntifs\ns-ntifs-_reparse_data_buffer.md">REPARSE_DATA_BUFFER</a> structure instead of the REPARSE_GUID_DATA_BUFFER structure. However, third-party reparse points are required to use the REPARSE_GUID_DATA_BUFFER structure. 

Reparse point tags are assigned to third parties by Microsoft. You may request more than one reparse point for use with a file system, file system filter driver, or minifilter driver. For more information about requesting a reparse point tag from Microsoft, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=8706">Windows IFS Kit</a> website. 

Reparse point GUIDs are not assigned by Microsoft. However, you must choose one GUID to use with your assigned reparse point tag, and you must always use this GUID with the tag. To generate a GUID, you should use GUIDGen (<i>Guidgen.exe</i>), a tool that is included in the Microsoft Windows SDK. 

Minifilters can set or delete a reparse point by calling <a href="..\fltkernel\nf-fltkernel-flttagfile.md">FltTagFile</a> or <a href="..\fltkernel\nf-fltkernel-fltuntagfile.md">FltUntagFile</a>. Minifilters can retrieve a reparse point by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544836">FSCTL_GET_REPARSE_POINT</a> control code. This code can be sent to the file system by calling <a href="..\fltkernel\nf-fltkernel-fltfscontrolfile.md">FltFsControlFile</a>. 

File systems and filter drivers can retrieve, set, or delete a reparse point by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544836">FSCTL_GET_REPARSE_POINT</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff545568">FSCTL_SET_REPARSE_POINT</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff544828">FSCTL_DELETE_REPARSE_POINT</a> control codes. These codes can be sent to the file system by calling <a href="..\ntifs\nf-ntifs-zwfscontrolfile.md">ZwFsControlFile</a>. 

For more information about reparse points and reparse point tags, see the Windows SDK documentation.  



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltfscontrolfile.md">FltFsControlFile</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544705">FLT_PARAMETERS for IRP_MJ_FILE_SYSTEM_CONTROL</a>

<a href="..\fltkernel\nf-fltkernel-flttagfile.md">FltTagFile</a>

<a href="..\ntifs\ns-ntifs-_file_reparse_point_information.md">FILE_REPARSE_POINT_INFORMATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550751">IRP_MJ_FILE_SYSTEM_CONTROL</a>

<a href="..\ntifs\nf-ntifs-isreparsetagnamesurrogate.md">IsReparseTagNameSurrogate</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544828">FSCTL_DELETE_REPARSE_POINT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544836">FSCTL_GET_REPARSE_POINT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545568">FSCTL_SET_REPARSE_POINT</a>

<a href="..\fltkernel\nf-fltkernel-fltuntagfile.md">FltUntagFile</a>

<a href="..\ntifs\nf-ntifs-isreparsetagmicrosoft.md">IsReparseTagMicrosoft</a>

<a href="..\ntifs\nf-ntifs-zwfscontrolfile.md">ZwFsControlFile</a>

<a href="..\ntifs\ns-ntifs-_reparse_data_buffer.md">REPARSE_DATA_BUFFER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20REPARSE_GUID_DATA_BUFFER structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

