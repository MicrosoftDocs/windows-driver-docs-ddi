---
UID: NF:fltkernel.FltUnregisterFilter
title: FltUnregisterFilter function
author: windows-driver-content
description: A registered minifilter driver calls FltUnregisterFilter to unregister itself so that the Filter Manager no longer calls it to process I/O operations.
old-location: ifsk\fltunregisterfilter.htm
old-project: ifsk
ms.assetid: 5369566b-fa64-4aec-ad3e-1a129bcefdd6
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , F, FltApiRef_p_to_z_cedf94f0-1f4a-46cf-aa81-914ab30d2a98.xml, FltUnregisterFilter, FltUnregisterFilter function [Installable File System Drivers], U, e, fltkernel/FltUnregisterFilter, g, i, ifsk.fltunregisterfilter, l, n, r, s, t"
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
-	FltUnregisterFilter
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltUnregisterFilter function


## -description


A registered minifilter driver calls <b>FltUnregisterFilter</b> to unregister itself so that the Filter Manager no longer calls it to process I/O operations. 


## -syntax


````
VOID FltUnregisterFilter(
  _In_ PFLT_FILTER Filter
);
````


## -parameters




### -param Filter [in]

Opaque filter pointer returned by <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>. 


## -returns



None 




## -remarks



<b>FltUnregisterFilter</b> unregisters the minifilter driver's callback routines and removes any contexts that the minifilter driver has set on files, volumes, instances, streams, or stream handles. It also calls the minifilter driver's <i>InstanceTeardownStartCallback</i> and <i>InstanceTeardownCompleteCallback</i> (<a href="..\fltkernel\nc-fltkernel-pflt_instance_teardown_callback.md">PFLT_INSTANCE_TEARDOWN_CALLBACK</a>) routines for each minifilter driver instance. 

A minifilter driver typically calls <b>FltUnregisterFilter</b> from its unload routine when it is about to be unloaded. 

A minifilter driver can only call <b>FltUnregisterFilter</b> to unregister itself, not another minifilter driver. 

To register a minifilter driver, call <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>. 




## -see-also

<a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a>



<a href="..\fltkernel\nc-fltkernel-pflt_instance_teardown_callback.md">PFLT_INSTANCE_TEARDOWN_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_filter_unload_callback.md">PFLT_FILTER_UNLOAD_CALLBACK</a>



<a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltUnregisterFilter function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

