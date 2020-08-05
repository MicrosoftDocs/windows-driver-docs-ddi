---
UID: NS:fltkernel._FLT_NAME_CONTROL
title: _FLT_NAME_CONTROL (fltkernel.h)
description: A minifilter that provides file names for the Filter Manager's name cache can use the FLT_NAME_CONTROL structure to manage its name buffers.
old-location: ifsk\flt_name_control.htm
tech.root: ifsk
ms.assetid: 0f796ad1-e4b4-4113-b076-ed6c9ea711c9
ms.date: 04/16/2018
keywords: ["FLT_NAME_CONTROL structure"]
ms.keywords: "*PFLT_NAME_CONTROL, FLT_NAME_CONTROL, FLT_NAME_CONTROL structure [Installable File System Drivers], FltSystemStructures_691a74ca-7671-44e3-9072-5d081c508a6c.xml, PFLT_NAME_CONTROL, PFLT_NAME_CONTROL structure pointer [Installable File System Drivers], _FLT_NAME_CONTROL, fltkernel/FLT_NAME_CONTROL, fltkernel/PFLT_NAME_CONTROL, ifsk.flt_name_control"
f1_keywords:
 - "fltkernel/FLT_NAME_CONTROL"
 - "FLT_NAME_CONTROL"
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
- fltkernel.h
api_name:
- FLT_NAME_CONTROL
targetos: Windows
req.typenames: FLT_NAME_CONTROL, *PFLT_NAME_CONTROL
---

# _FLT_NAME_CONTROL structure


## -description


A minifilter that provides file names for the Filter Manager's name cache can use the FLT_NAME_CONTROL structure to manage its name buffers. 


## -struct-fields




### -field Name


<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the file name string. 


## -remarks



Minifilters must not attempt to free or replace the buffer in the <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure  that the <b>Name</b> member points to directly. Instead, minifilters should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcheckandgrownamecontrol">FltCheckAndGrowNameControl</a> to obtain a larger name control buffer. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcheckandgrownamecontrol">FltCheckAndGrowNameControl</a>



<a href="https://docs.microsoft.com/previous-versions/ff543030(v=vs.85)">FltGetFileNameFormat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformation">FltGetFileNameInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformationunsafe">FltGetFileNameInformationUnsafe</a>



<a href="https://docs.microsoft.com/previous-versions/ff543040(v=vs.85)">FltGetFileNameQueryMethod</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

