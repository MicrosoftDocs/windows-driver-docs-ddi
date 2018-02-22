---
UID: NF:ntifs.IsReparseTagMicrosoft
title: IsReparseTagMicrosoft macro
author: windows-driver-content
description: The IsReparseTagMicrosoft macro determines whether a reparse point tag indicates a Microsoft reparse point.
old-location: ifsk\isreparsetagmicrosoft.htm
old-project: ifsk
ms.assetid: 9c5abef5-36ff-4f10-8e4e-b8d36d995246
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ifsk.isreparsetagmicrosoft, IsReparseTagMicrosoft, IsReparseTagMicrosoft function [Installable File System Drivers], ioref_ef573233-e933-490e-b762-1ce20343c65c.xml, ntifs/IsReparseTagMicrosoft
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
-	IsReparseTagMicrosoft
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IsReparseTagMicrosoft macro


## -description


The <b>IsReparseTagMicrosoft</b> macro determines whether a reparse point tag indicates a Microsoft reparse point. 


## -syntax


````
ULONG IsReparseTagMicrosoft(
  _In_ ULONG _tag
);
````


## -parameters




### -param _tag [in]

Reparse point tag to be tested. 


## -remarks



Only Microsoft reparse points can use Microsoft tags. Third-party reparse points must use non-Microsoft tags. However, third-party drivers can set Microsoft reparse points. For more information, see the Remarks section of the reference entry for the <a href="..\ntifs\ns-ntifs-_reparse_guid_data_buffer.md">REPARSE_GUID_DATA_BUFFER</a> structure. 

For more information about reparse points, see the Microsoft Windows SDK documentation. 




## -see-also

<a href="..\ntifs\nf-ntifs-zwfscontrolfile.md">ZwFsControlFile</a>



<a href="..\fltkernel\nf-fltkernel-fltuntagfile.md">FltUntagFile</a>



<a href="..\ntifs\nf-ntifs-zwfscontrolfile.md">ZwFsControlFile</a>



<a href="..\fltkernel\nf-fltkernel-flttagfile.md">FltTagFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544836">FSCTL_GET_REPARSE_POINT</a>



<a href="..\ntifs\nf-ntifs-isreparsetagnamesurrogate.md">IsReparseTagNameSurrogate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545568">FSCTL_SET_REPARSE_POINT</a>



<a href="..\fltkernel\nf-fltkernel-fltfscontrolfile.md">FltFsControlFile</a>



<a href="..\ntifs\ns-ntifs-_reparse_guid_data_buffer.md">REPARSE_GUID_DATA_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545568">FSCTL_SET_REPARSE_POINT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IsReparseTagMicrosoft function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

