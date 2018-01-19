---
UID: NF:fltkernel.FltGetFileSystemType
title: FltGetFileSystemType function
author: windows-driver-content
description: The FltGetFileSystemType function takes a volume or instance object and provides the file system type of the volume.
old-location: ifsk\fltgetfilesystemtype.htm
old-project: ifsk
ms.assetid: 9e603d0f-74e7-4715-b3dc-4a9623f98dde
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltGetFileSystemType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltGetFileSystemType
req.alt-loc: FltMgr.sys
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
req.typenames: EXpsFontRestriction
---

# FltGetFileSystemType function



## -description
The <b>FltGetFileSystemType</b> function takes a volume or instance object and provides the file system type of the volume.



## -syntax

````
NTSTATUS FltGetFileSystemType(
  _In_  PVOID                FltObject,
  _Out_ PFLT_FILESYSTEM_TYPE FileSystemType
);
````


## -parameters

### -param FltObject [in]

A pointer to a filter object. This can be a FLT_INSTANCE or FLT_VOLUME object. 


### -param FileSystemType [out]

A pointer to a user allocated FLT_FILESYSTEM_TYPE object that receives the file system type for <i>FltObject</i>. 


## -returns
<b>FltGetFileSystemType</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>FltObject</i> object was not a FLT_INSTANCE  or FLT_VOLUME  object. 

 


## -remarks
If an instance is passed as the <i>FltObject</i>, <b>FltGetFileSystemType</b> provides the file system type for the volume referred to by the instance object. 

If STATUS_INVALID_PARAMETER is returned, the <i>FileSystemType</i> parameter is set to FLT_FSTYPE_UNKNOWN. 


## -see-also
<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumefromfileobject.md">FltGetVolumeFromFileObject</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumefrominstance.md">FltGetVolumeFromInstance</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumefromname.md">FltGetVolumeFromName</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumeguidname.md">FltGetVolumeGuidName</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumeinformation.md">FltGetVolumeInformation</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumeinstancefromname.md">FltGetVolumeInstanceFromName</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumename.md">FltGetVolumeName</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumeproperties.md">FltGetVolumeProperties</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltisvolumewritable.md">FltIsVolumeWritable</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetFileSystemType function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

