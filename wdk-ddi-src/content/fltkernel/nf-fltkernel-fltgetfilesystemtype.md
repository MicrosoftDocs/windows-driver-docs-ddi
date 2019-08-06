---
UID: NF:fltkernel.FltGetFileSystemType
title: FltGetFileSystemType function (fltkernel.h)
description: The FltGetFileSystemType function takes a volume or instance object and provides the file system type of the volume.
old-location: ifsk\fltgetfilesystemtype.htm
tech.root: ifsk
ms.assetid: 9e603d0f-74e7-4715-b3dc-4a9623f98dde
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_00fe70b3-cc15-4272-a4df-653c05abfeb1.xml, FltGetFileSystemType, FltGetFileSystemType function [Installable File System Drivers], fltkernel/FltGetFileSystemType, ifsk.fltgetfilesystemtype
ms.topic: function
f1_keywords:
 - "fltkernel/FltGetFileSystemType"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows Vista.
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
req.lib: FltMgr.lib
req.dll: FltMgr.sys
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- FltMgr.sys
api_name:
- FltGetFileSystemType
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetFileSystemType function


## -description


The <b>FltGetFileSystemType</b> function takes a volume or instance object and provides the file system type of the volume.


## -parameters




### -param FltObject [in]

A pointer to a filter object. This can be a FLT_INSTANCE or FLT_VOLUME object. 


### -param FileSystemType [out]

A pointer to a user allocated FLT_FILESYSTEM_TYPE object that receives the file system type for <i>FltObject</i>. 


## -returns



<b>FltGetFileSystemType</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>FltObject</i> object was not a FLT_INSTANCE  or FLT_VOLUME  object. 

</td>
</tr>
</table>
 




## -remarks



If an instance is passed as the <i>FltObject</i>, <b>FltGetFileSystemType</b> provides the file system type for the volume referred to by the instance object. 

If STATUS_INVALID_PARAMETER is returned, the <i>FileSystemType</i> parameter is set to FLT_FSTYPE_UNKNOWN. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetvolumefromfileobject">FltGetVolumeFromFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetvolumefrominstance">FltGetVolumeFromInstance</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetvolumefromname">FltGetVolumeFromName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetvolumeguidname">FltGetVolumeGuidName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetvolumeinformation">FltGetVolumeInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetvolumeinstancefromname">FltGetVolumeInstanceFromName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetvolumename">FltGetVolumeName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetvolumeproperties">FltGetVolumeProperties</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltisvolumewritable">FltIsVolumeWritable</a>
 

 

