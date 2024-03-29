---
UID: NF:fltkernel.FltReleaseFileNameInformation
title: FltReleaseFileNameInformation function (fltkernel.h)
description: FltReleaseFileNameInformation releases a file name information structure.
old-location: ifsk\fltreleasefilenameinformation.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltReleaseFileNameInformation function"]
ms.keywords: FltApiRef_p_to_z_c5266e1d-ab6a-406d-a319-2e9cc2f1acb4.xml, FltReleaseFileNameInformation, FltReleaseFileNameInformation function [Installable File System Drivers], fltkernel/FltReleaseFileNameInformation, ifsk.fltreleasefilenameinformation
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltReleaseFileNameInformation
 - fltkernel/FltReleaseFileNameInformation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltReleaseFileNameInformation
---

# FltReleaseFileNameInformation function


## -description

<b>FltReleaseFileNameInformation</b> releases a file name information structure.

## -parameters

### -param FileNameInformation [in]


Pointer to the FLT_FILE_NAME_INFORMATION structure to be released. This parameter is required and cannot be <b>NULL</b>.

## -returns

None

## -remarks

<b>FltReleaseFileNameInformation</b> decrements the reference count on a file name information (<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_file_name_information">FLT_FILE_NAME_INFORMATION</a>) structure returned by a previous call to <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetdestinationfilenameinformation">FltGetDestinationFileNameInformation</a>, <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformation">FltGetFileNameInformation</a>, <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformationunsafe">FltGetFileNameInformationUnsafe</a>, or <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgettunneledname">FltGetTunneledName</a>. When this reference count reaches zero, the structure is freed. 

To increment the reference count on a file name information structure, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreferencefilenameinformation">FltReferenceFileNameInformation</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_file_name_information">FLT_FILE_NAME_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetdestinationfilenameinformation">FltGetDestinationFileNameInformation</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformation">FltGetFileNameInformation</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformationunsafe">FltGetFileNameInformationUnsafe</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgettunneledname">FltGetTunneledName</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreferencefilenameinformation">FltReferenceFileNameInformation</a>
