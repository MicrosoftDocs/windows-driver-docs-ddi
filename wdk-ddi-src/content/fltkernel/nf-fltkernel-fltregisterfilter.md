---
UID: NF:fltkernel.FltRegisterFilter
title: FltRegisterFilter function (fltkernel.h)
description: FltRegisterFilter registers a minifilter driver.
old-location: ifsk\fltregisterfilter.htm
tech.root: ifsk
ms.assetid: 46e96f85-d368-40cd-9530-81959d20b750
ms.date: 04/16/2018
keywords: ["FltRegisterFilter function"]
ms.keywords: FltApiRef_p_to_z_41e3002c-d720-4e0f-81cb-36cbc215cdba.xml, FltRegisterFilter, FltRegisterFilter function [Installable File System Drivers], fltkernel/FltRegisterFilter, ifsk.fltregisterfilter
f1_keywords:
 - "fltkernel/FltRegisterFilter"
 - "FltRegisterFilter"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltRegisterFilter
targetos: Windows
req.typenames: 
---

# FltRegisterFilter function


## -description


<b>FltRegisterFilter</b> registers a minifilter driver. 


## -parameters




### -param Driver 
[in]
A pointer to the driver object for the minifilter driver. This should be the same driver object pointer that was passed as input to the minifilter driver's <b>DriverEntry</b> routine. 


### -param Registration 
[in]
A pointer to a caller-allocated minifilter driver registration structure (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_registration">FLT_REGISTRATION</a>). 


### -param RetFilter 
[out]
A pointer to a caller-allocated variable that receives an opaque filter pointer for the caller. 


## -returns



<b>FltRegisterFilter</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltRegisterFilter</b> encountered a pool allocation failure. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the following: 

<ul>
<li>
The <b>Version</b> member of the <i>Registration</i> structure was not set to FLT_REGISTRATION_VERSION. 

</li>
<li>
One of the non-NULL name-provider routines in the <i>Registration</i> structure was set to an invalid value. The <b>GenerateFileNameCallback</b>, <b>NormalizeNameComponentCallback</b>, and <b>NormalizeNameComponentExCallback</b> members of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_registration">FLT_REGISTRATION</a> point to the name-provider routines. 

</li>
</ul>
STATUS_INVALID_PARAMETER is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_NOT_INITIALIZED</b></dt>
</dl>
</td>
<td width="60%">
The Filter Manager was not initialized when the filter tried to register. Make sure that the Filter Manager is loaded as a driver. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The filter service key is not found in the registry.

-or-

The filter instance is not registered.

</td>
</tr>
</table>
 




## -remarks



Every minifilter driver must call <b>FltRegisterFilter</b> from its <b>DriverEntry</b> routine to add itself to the global list of registered minifilter drivers and to provide the Filter Manager with a list of callback functions and other information about the minifilter driver. 

<b>FltRegisterFilter</b> returns an opaque filter pointer for the minifilter driver in *<i>RetFilter</i>. This pointer value uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded. The minifilter driver should save this pointer, because it is a required parameter for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltstartfiltering">FltStartFiltering</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltunregisterfilter">FltUnregisterFilter</a>. 

After calling <b>FltRegisterFilter</b>, a minifilter driver typically calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltstartfiltering">FltStartFiltering</a> to begin filtering I/O operations. 

A minifilter driver can only call <b>FltRegisterFilter</b> to register itself, not another minifilter driver. 

To unregister itself, a minifilter driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltunregisterfilter">FltUnregisterFilter</a>.. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_registration">FLT_REGISTRATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltstartfiltering">FltStartFiltering</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltunregisterfilter">FltUnregisterFilter</a>
 

 

