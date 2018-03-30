---
UID: NC:fltkernel.PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK
title: PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK
author: windows-driver-content
description: A minifilter driver can register a routine of type PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK as the minifilter driver's InstanceQueryTeardownCallback routine.
old-location: ifsk\pflt_instance_query_teardown_callback.htm
old-project: ifsk
ms.assetid: 5aa41472-cb1d-49ba-a546-ec42bb859552
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltCallbacks_2ef837ae-a56a-4e66-a8d3-1f049f7bad45.xml, InstanceQueryTeardownCallback, InstanceQueryTeardownCallback routine [Installable File System Drivers], PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK, fltkernel/InstanceQueryTeardownCallback, ifsk.pflt_instance_query_teardown_callback
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
-	InstanceQueryTeardownCallback
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK callback


## -description


A minifilter driver can register a routine of type <i>PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</i> as the minifilter driver's <i>InstanceQueryTeardownCallback</i> routine. 


## -parameters




### -param FltObjects [in]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a> structure that contains opaque pointers for the objects related to the current operation. 


### -param Flags [in]

Bitmask of flags that describe why the given instance query teardown callback routine was called. No flags are currently defined. 


## -returns



This callback routine returns <b>STATUS_SUCCESS</b> or an <b>NTSTATUS</b> value such as one of the following: 

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
Returning this status value prevents the minifilter driver instance from being detached. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



When a minifilter driver registers itself by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a> from its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine, it can register a routine of type <i>PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</i> as the minifilter driver's <i>InstanceQueryTeardownCallback</i> routine. 

To register the <i>InstanceQueryTeardownCallback</i> routine, the minifilter driver stores the address of a routine of type <i>PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK</i> in the <i>InstanceQueryTeardownCallback</i> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544811">FLT_REGISTRATION</a> structure that the minifilter driver passes as the <i>Registration</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>. 

The filter manager calls this routine to allow the minifilter driver to respond to a manual detach request. Such a request is received when a user-mode application calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff540475">FilterDetach</a> or a kernel-mode component calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff542041">FltDetachVolume</a>. 

This routine is not called for automatic or mandatory detach requests, for example, when the minifilter driver is unloaded or a volume is dismounted. 

If this routine returns an error or warning <b>NTSTATUS</b> code, such as <b>STATUS_FLT_DO_NOT_DETACH</b>, the minifilter driver instance is not detached from the volume. Otherwise, the instance is detached. 

If a minifilter driver does not define an <i>InstanceQueryTeardownCallback</i> routine, its instances cannot be detached manually by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff540475">FilterDetach</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff542041">FltDetachVolume</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544811">FLT_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540475">FilterDetach</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542041">FltDetachVolume</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551096">PFLT_INSTANCE_SETUP_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551098">PFLT_INSTANCE_TEARDOWN_CALLBACK</a>
 

 

