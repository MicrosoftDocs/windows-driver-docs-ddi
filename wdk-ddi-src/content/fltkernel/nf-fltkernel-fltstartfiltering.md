---
UID: NF:fltkernel.FltStartFiltering
title: FltStartFiltering function (fltkernel.h)
description: FltStartFiltering starts filtering for a registered minifilter driver.
old-location: ifsk\fltstartfiltering.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltStartFiltering function"]
ms.keywords: FltApiRef_p_to_z_f88abc20-f8b7-4399-85be-bd43674fe536.xml, FltStartFiltering, FltStartFiltering function [Installable File System Drivers], fltkernel/FltStartFiltering, ifsk.fltstartfiltering
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
 - FltStartFiltering
 - fltkernel/FltStartFiltering
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltStartFiltering
---

# FltStartFiltering function


## -description

<b>FltStartFiltering</b> starts filtering for a registered minifilter driver.

## -parameters

### -param Filter 

[in]
Opaque filter pointer returned by <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfilter">FltRegisterFilter</a>.

## -returns

<b>FltStartFiltering</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

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
Filtering was already started for this minifilter driver. This is an error code. 

</td>
</tr>
</table>

## -remarks

A minifilter driver typically calls <b>FltStartFiltering</b> from its <b>DriverEntry</b> routine after it has completed its global initialization and called <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfilter">FltRegisterFilter</a>. <b>FltStartFiltering</b> notifies the Filter Manager that the minifilter driver is ready to begin attaching to volumes and filtering I/O requests. After the minifilter driver calls this routine, the Filter Manager treats the minifilter driver as a fully active minifilter driver, presenting it with volumes to attach to, as well as I/O requests. The minifilter driver must be prepared to begin receiving these notifications and I/O requests even before <b>FltStartFiltering</b> returns.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltregisterfilter">FltRegisterFilter</a>
