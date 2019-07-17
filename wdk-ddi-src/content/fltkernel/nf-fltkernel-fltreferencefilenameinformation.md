---
UID: NF:fltkernel.FltReferenceFileNameInformation
title: FltReferenceFileNameInformation function (fltkernel.h)
description: FltReferenceFileNameInformation increments the reference count on a file name information structure.
old-location: ifsk\fltreferencefilenameinformation.htm
tech.root: ifsk
ms.assetid: d2df37f3-78f7-4e44-9139-2c2e569bb48d
ms.date: 04/16/2018
ms.keywords: FltApiRef_p_to_z_c6cfa7ad-ac72-45ad-9750-c466dd6ede6e.xml, FltReferenceFileNameInformation, FltReferenceFileNameInformation function [Installable File System Drivers], fltkernel/FltReferenceFileNameInformation, ifsk.fltreferencefilenameinformation
ms.topic: function
f1_keywords:
 - "fltkernel/FltReferenceFileNameInformation"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltReferenceFileNameInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltReferenceFileNameInformation function


## -description


<b>FltReferenceFileNameInformation</b> increments the reference count on a file name information structure. 


## -parameters




### -param FileNameInformation [in]

Pointer to the file name information (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_file_name_information">FLT_FILE_NAME_INFORMATION</a>) structure. This parameter is required and cannot be <b>NULL</b>. 


## -returns



None




## -remarks



<b>FltReferenceFileNameInformation</b> increments the reference count on a file name information (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_file_name_information">FLT_FILE_NAME_INFORMATION</a>) structure returned by a previous call to a file name query routine such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetfilenameinformation">FltGetFileNameInformation</a>. 

After a successful call to <b>FltReferenceFileNameInformation</b>, the caller is responsible for decrementing the reference count on the file name information structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltreleasefilenameinformation">FltReleaseFileNameInformation</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_file_name_information">FLT_FILE_NAME_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetdestinationfilenameinformation">FltGetDestinationFileNameInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetfilenameinformation">FltGetFileNameInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgetfilenameinformationunsafe">FltGetFileNameInformationUnsafe</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltgettunneledname">FltGetTunneledName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltreleasefilenameinformation">FltReleaseFileNameInformation</a>
 

 

