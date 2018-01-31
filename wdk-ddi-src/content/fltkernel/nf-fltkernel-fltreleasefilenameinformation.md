---
UID: NF:fltkernel.FltReleaseFileNameInformation
title: FltReleaseFileNameInformation function
author: windows-driver-content
description: FltReleaseFileNameInformation releases a file name information structure.
old-location: ifsk\fltreleasefilenameinformation.htm
old-project: ifsk
ms.assetid: 352dbab6-76c3-4e67-a226-4c3d83fbb3b6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltApiRef_p_to_z_c5266e1d-ab6a-406d-a319-2e9cc2f1acb4.xml, FltReleaseFileNameInformation function [Installable File System Drivers], FltReleaseFileNameInformation, fltkernel/FltReleaseFileNameInformation, ifsk.fltreleasefilenameinformation
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
-	FltReleaseFileNameInformation
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltReleaseFileNameInformation function


## -description


<b>FltReleaseFileNameInformation</b> releases a file name information structure. 


## -syntax


````
VOID FltReleaseFileNameInformation(
  _In_ PFLT_FILE_NAME_INFORMATION FileNameInformation
);
````


## -parameters




#### - FileNameInformation [in]

Pointer to the FLT_FILE_NAME_INFORMATION structure to be released. This parameter is required and cannot be <b>NULL</b>. 


## -returns


None 



## -remarks


<b>FltReleaseFileNameInformation</b> decrements the reference count on a file name information (<a href="..\fltkernel\ns-fltkernel-_flt_file_name_information.md">FLT_FILE_NAME_INFORMATION</a>) structure returned by a previous call to <a href="..\fltkernel\nf-fltkernel-fltgetdestinationfilenameinformation.md">FltGetDestinationFileNameInformation</a>, <a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformation.md">FltGetFileNameInformation</a>, <a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformationunsafe.md">FltGetFileNameInformationUnsafe</a>, or <a href="..\fltkernel\nf-fltkernel-fltgettunneledname.md">FltGetTunneledName</a>. When this reference count reaches zero, the structure is freed. 

To increment the reference count on a file name information structure, call <a href="..\fltkernel\nf-fltkernel-fltreferencefilenameinformation.md">FltReferenceFileNameInformation</a>. 



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformation.md">FltGetFileNameInformation</a>

<a href="..\fltkernel\nf-fltkernel-fltgettunneledname.md">FltGetTunneledName</a>

<a href="..\fltkernel\ns-fltkernel-_flt_file_name_information.md">FLT_FILE_NAME_INFORMATION</a>

<a href="..\fltkernel\nf-fltkernel-fltreferencefilenameinformation.md">FltReferenceFileNameInformation</a>

<a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformationunsafe.md">FltGetFileNameInformationUnsafe</a>

<a href="..\fltkernel\nf-fltkernel-fltgetdestinationfilenameinformation.md">FltGetDestinationFileNameInformation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltReleaseFileNameInformation function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

