---
UID: NC:fltkernel.PFLT_FILTER_UNLOAD_CALLBACK
title: PFLT_FILTER_UNLOAD_CALLBACK
author: windows-driver-content
description: A minifilter driver can register a routine of type PFLT_FILTER_UNLOAD_CALLBACK as the minifilter driver's FilterUnloadCallback routine.
old-location: ifsk\pflt_filter_unload_callback.htm
old-project: ifsk
ms.assetid: 746f13f5-c92d-4dae-8fd7-4c9fdfa9e044
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FilterUnloadCallback, FilterUnloadCallback routine [Installable File System Drivers], FltCallbacks_e28b1a16-b974-493a-8ab5-7b6004d66268.xml, PFLT_FILTER_UNLOAD_CALLBACK, fltkernel/FilterUnloadCallback, ifsk.pflt_filter_unload_callback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	fltkernel.h
api_name:
-	FilterUnloadCallback
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# PFLT_FILTER_UNLOAD_CALLBACK callback


## -description


A minifilter driver can register a routine of type PFLT_FILTER_UNLOAD_CALLBACK as the minifilter driver's <i>FilterUnloadCallback</i> routine. 


## -parameters




### -param Flags

Bitmask of flags describing the unload request. This parameter can be <b>NULL</b> or the following: 

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLTFL_FILTER_UNLOAD_MANDATORY

</td>
<td>
The filter manager sets this flag to indicate that the unload operation is mandatory. 

</td>
</tr>
</table>
 


## -returns



This callback routine returns STATUS_SUCCESS or an NTSTATUS value such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DO_NOT_DETACH</b></dt>
</dl>
</td>
<td width="60%">
If the unload operation is not mandatory, returning this status value prevents the minifilter driver from being unloaded. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



When a minifilter driver registers itself by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>, it can register a <i>FilterUnloadCallback</i> routine. To register this callback routine, the minifilter driver stores the address of a routine of type PFLT_FILTER_UNLOAD_CALLBACK in the <b>FilterUnloadCallback</b> field of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544811">FLT_REGISTRATION</a> structure that the minifilter driver passes as a parameter to <b>FltRegisterFilter</b>. 

Minifilter drivers are not required to register a <i>FilterUnloadCallback</i> routine. However, registering an unload routine is strongly recommended. If a minifilter driver does not register a <i>FilterUnloadCallback</i> routine, it cannot be unloaded. 

The filter manager calls the minifilter driver's <i>FilterUnloadCallback</i> routine to notify the minifilter driver that the filter manager is about to unload the minifilter driver. 

If the unload operation is not mandatory, and the <i>FilterUnloadCallback</i> routine returns an error or warning NTSTATUS code, such as STATUS_FLT_DO_NOT_DETACH, the minifilter driver is not unloaded. Otherwise, the minifilter driver is unloaded. 

If the FLTFL_FILTER_UNLOAD_MANDATORY flag is set in the <i>Flags</i> parameter, the unload operation is mandatory, and the minifilter driver cannot prevent itself from being unloaded. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544811">FLT_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>
 

 

