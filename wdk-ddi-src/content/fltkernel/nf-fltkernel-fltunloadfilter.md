---
UID: NF:fltkernel.FltUnloadFilter
title: FltUnloadFilter function (fltkernel.h)
description: A minifilter driver that has loaded a supporting minifilter driver by calling FltLoadFilter can unload the minifilter driver by calling FltUnloadFilter.
old-location: ifsk\fltunloadfilter.htm
tech.root: ifsk
ms.assetid: 234907d8-d21e-4303-9508-0673afa471a6
ms.date: 04/16/2018
ms.keywords: FltApiRef_p_to_z_88925df3-96d3-4e1f-9e0b-f97eb8d9b40b.xml, FltUnloadFilter, FltUnloadFilter function [Installable File System Drivers], fltkernel/FltUnloadFilter, ifsk.fltunloadfilter
f1_keywords:
 - "fltkernel/FltUnloadFilter"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltUnloadFilter
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltUnloadFilter function


## -description


A minifilter driver that has loaded a supporting minifilter driver by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltloadfilter">FltLoadFilter</a> can unload the minifilter driver by calling <b>FltUnloadFilter</b>. 


## -parameters




### -param FilterName [in]

Pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure containing the minifilter driver service name that was passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltloadfilter">FltLoadFilter</a>. 


## -returns



<b>FltUnloadFilter</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
A matching minifilter driver was found, but it is already being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_FILTER_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No matching minifilter driver was found. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



A minifilter driver that has a dependency on another minifilter driver can unload that minifilter driver by calling <b>FltUnloadFilter</b>. This routine searches for a registered minifilter driver whose service name matches the given <i>FilterName</i> and calls that minifilter driver's <i>FilterUnloadCallback</i> (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_filter_unload_callback">PFLT_FILTER_UNLOAD_CALLBACK</a>) routine. 

If the supporting minifilter driver did not register a <i>FilterUnloadCallback</i> routine, the call to <b>FltUnloadFilter</b> fails. 

A minifilter driver cannot call <b>FltUnloadFilter</b> to unload itself. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltloadfilter">FltLoadFilter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_filter_unload_callback">PFLT_FILTER_UNLOAD_CALLBACK</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

