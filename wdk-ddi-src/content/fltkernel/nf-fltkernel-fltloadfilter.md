---
UID: NF:fltkernel.FltLoadFilter
title: FltLoadFilter function
author: windows-driver-content
description: The FltLoadFilter routine dynamically loads a minifilter driver into the currently running system.
old-location: ifsk\fltloadfilter.htm
old-project: ifsk
ms.assetid: aecf5f5f-c0b7-487a-9db0-d01212aef094
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ifsk.fltloadfilter, fltkernel/FltLoadFilter, FltLoadFilter, FltLoadFilter routine [Installable File System Drivers], FltApiRef_e_to_o_3cdd26c1-dc25-4fa0-8ea1-a1458742cd45.xml
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltLoadFilter
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltLoadFilter function


## -description


The <b>FltLoadFilter</b> routine dynamically loads a minifilter driver into the currently running system. 


## -syntax


````
NTSTATUS FltLoadFilter(
  _In_ PCUNICODE_STRING FilterName
);
````


## -parameters




### -param FilterName [in]

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure containing the service name for the minifilter driver. 


## -returns



<b>FltLoadFilter</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DRIVER_FAILED_PRIOR_UNLOAD</b></dt>
</dl>
</td>
<td width="60%">
The minifilter driver could not be loaded because a previous version of the driver is still in memory. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FAILED_DRIVER_ENTRY</b></dt>
</dl>
</td>
<td width="60%">
The minifilter driver's <b>DriverEntry</b> routine returned an NTSTATUS value that was not a success code. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IMAGE_ALREADY_LOADED</b></dt>
</dl>
</td>
<td width="60%">
The minifilter driver is already running. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No matching minifilter driver was found. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



A minifilter driver that has a dependency on another minifilter driver can load that minifilter driver by calling <b>FltLoadFilter</b>. 

To unload the supporting minifilter driver, call <a href="..\fltkernel\nf-fltkernel-fltunloadfilter.md">FltUnloadFilter</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltunloadfilter.md">FltUnloadFilter</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltLoadFilter routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

