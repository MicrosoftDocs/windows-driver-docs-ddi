---
UID: NF:ntifs.IsReparseTagNameSurrogate
title: IsReparseTagNameSurrogate macro
author: windows-driver-content
description: The IsReparseTagNameSurrogate macro determines whether a tag's associated reparse point is a surrogate for another named entity, such as a volume mount point.
old-location: ifsk\isreparsetagnamesurrogate.htm
old-project: ifsk
ms.assetid: 51e80cd6-19c1-4e21-b676-662c77840a8b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/IsReparseTagNameSurrogate, IsReparseTagNameSurrogate function [Installable File System Drivers], ioref_f44ef76c-2211-43a1-b151-a5804c7cd361.xml, IsReparseTagNameSurrogate, ifsk.isreparsetagnamesurrogate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: ntifs.h
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	IsReparseTagNameSurrogate
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IsReparseTagNameSurrogate macro


## -description


The <b>IsReparseTagNameSurrogate</b> macro determines whether a tag's associated reparse point is a surrogate for another named entity, such as a volume mount point. 


## -syntax


````
ULONG IsReparseTagNameSurrogate(
  _In_ ULONG _tag
);
````


## -parameters




#### - _tag [in]

Reparse point tag to be tested. 


## -remarks


If the name surrogate bit is set in the reparse tag, the file or directory represents another named entity in the system, such as a volume mount point. 

For more information about reparse points and volume mount points, see the Microsoft Windows SDK documentation. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544836">FSCTL_GET_REPARSE_POINT</a>

<a href="..\fltkernel\nf-fltkernel-fltfscontrolfile.md">FltFsControlFile</a>

<a href="..\ntifs\ns-ntifs-_reparse_data_buffer.md">REPARSE_DATA_BUFFER</a>

<a href="..\fltkernel\nf-fltkernel-flttagfile.md">FltTagFile</a>

<a href="..\ntifs\nf-ntifs-zwfscontrolfile.md">ZwFsControlFile</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545568">FSCTL_SET_REPARSE_POINT</a>

<a href="..\ntifs\nf-ntifs-isreparsetagmicrosoft.md">IsReparseTagMicrosoft</a>

<a href="..\fltkernel\nf-fltkernel-fltuntagfile.md">FltUntagFile</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544828">FSCTL_DELETE_REPARSE_POINT</a>

<a href="..\ntifs\ns-ntifs-_reparse_guid_data_buffer.md">REPARSE_GUID_DATA_BUFFER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IsReparseTagNameSurrogate function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

