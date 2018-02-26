---
UID: NF:fltkernel.FltReferenceFileNameInformation
title: FltReferenceFileNameInformation function
author: windows-driver-content
description: FltReferenceFileNameInformation increments the reference count on a file name information structure.
old-location: ifsk\fltreferencefilenameinformation.htm
old-project: ifsk
ms.assetid: d2df37f3-78f7-4e44-9139-2c2e569bb48d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , F, FltApiRef_p_to_z_c6cfa7ad-ac72-45ad-9750-c466dd6ede6e.xml, FltReferenceFileNameInformation, FltReferenceFileNameInformation function [Installable File System Drivers], I, N, R, a, c, e, f, fltkernel/FltReferenceFileNameInformation, i, ifsk.fltreferencefilenameinformation, l, m, n, o, r, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltReferenceFileNameInformation
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltReferenceFileNameInformation function


## -description


<b>FltReferenceFileNameInformation</b> increments the reference count on a file name information structure. 


## -syntax


````
VOID FltReferenceFileNameInformation(
  _In_ PFLT_FILE_NAME_INFORMATION FileNameInformation
);
````


## -parameters




### -param FileNameInformation [in]

Pointer to the file name information (<a href="..\fltkernel\ns-fltkernel-_flt_file_name_information.md">FLT_FILE_NAME_INFORMATION</a>) structure. This parameter is required and cannot be <b>NULL</b>. 


## -returns



None




## -remarks



<b>FltReferenceFileNameInformation</b> increments the reference count on a file name information (<a href="..\fltkernel\ns-fltkernel-_flt_file_name_information.md">FLT_FILE_NAME_INFORMATION</a>) structure returned by a previous call to a file name query routine such as <a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformation.md">FltGetFileNameInformation</a>. 

After a successful call to <b>FltReferenceFileNameInformation</b>, the caller is responsible for decrementing the reference count on the file name information structure by calling <a href="..\fltkernel\nf-fltkernel-fltreleasefilenameinformation.md">FltReleaseFileNameInformation</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltreleasefilenameinformation.md">FltReleaseFileNameInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformationunsafe.md">FltGetFileNameInformationUnsafe</a>



<a href="..\fltkernel\ns-fltkernel-_flt_file_name_information.md">FLT_FILE_NAME_INFORMATION</a>



<a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformation.md">FltGetFileNameInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltgetdestinationfilenameinformation.md">FltGetDestinationFileNameInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltgettunneledname.md">FltGetTunneledName</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltReferenceFileNameInformation function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

