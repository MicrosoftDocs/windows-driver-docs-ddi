---
UID: NF:fltkernel.FltRegisterFilter
title: FltRegisterFilter function
author: windows-driver-content
description: FltRegisterFilter registers a minifilter driver.
old-location: ifsk\fltregisterfilter.htm
old-project: ifsk
ms.assetid: 46e96f85-d368-40cd-9530-81959d20b750
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.fltregisterfilter, FltRegisterFilter function [Installable File System Drivers], FltApiRef_p_to_z_41e3002c-d720-4e0f-81cb-36cbc215cdba.xml, FltRegisterFilter, fltkernel/FltRegisterFilter
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
-	FltRegisterFilter
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltRegisterFilter function


## -description


<b>FltRegisterFilter</b> registers a minifilter driver. 


## -syntax


````
NTSTATUS FltRegisterFilter(
  _In_        PDRIVER_OBJECT   Driver,
  _In_  const FLT_REGISTRATION *Registration,
  _Out_       PFLT_FILTER      *RetFilter
);
````


## -parameters




#### - Driver [in]

A pointer to the driver object for the minifilter driver. This should be the same driver object pointer that was passed as input to the minifilter driver's <b>DriverEntry</b> routine. 


#### - Registration [in]

A pointer to a caller-allocated minifilter driver registration structure (<a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a>). 


#### - RetFilter [out]

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
One of the non-NULL name-provider routines in the <i>Registration</i> structure was set to an invalid value. The <b>GenerateFileNameCallback</b>, <b>NormalizeNameComponentCallback</b>, and <b>NormalizeNameComponentExCallback</b> members of <a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a> point to the name-provider routines. 

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

<b>FltRegisterFilter</b> returns an opaque filter pointer for the minifilter driver in *<i>RetFilter</i>. This pointer value uniquely identifies the minifilter driver and remains constant as long as the minifilter driver is loaded. The minifilter driver should save this pointer, because it is a required parameter for <a href="..\fltkernel\nf-fltkernel-fltstartfiltering.md">FltStartFiltering</a> and <a href="..\fltkernel\nf-fltkernel-fltunregisterfilter.md">FltUnregisterFilter</a>. 

After calling <b>FltRegisterFilter</b>, a minifilter driver typically calls <a href="..\fltkernel\nf-fltkernel-fltstartfiltering.md">FltStartFiltering</a> to begin filtering I/O operations. 

A minifilter driver can only call <b>FltRegisterFilter</b> to register itself, not another minifilter driver. 

To unregister itself, a minifilter driver calls <a href="..\fltkernel\nf-fltkernel-fltunregisterfilter.md">FltUnregisterFilter</a>.. 



## -see-also

<a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a>

<a href="..\fltkernel\nf-fltkernel-fltunregisterfilter.md">FltUnregisterFilter</a>

<a href="..\fltkernel\nf-fltkernel-fltstartfiltering.md">FltStartFiltering</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltRegisterFilter function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

