---
UID: NF:fltkernel.FltUnregisterFilter
title: FltUnregisterFilter function
author: windows-driver-content
description: A registered minifilter driver calls FltUnregisterFilter to unregister itself so that the Filter Manager no longer calls it to process I/O operations.
old-location: ifsk\fltunregisterfilter.htm
old-project: ifsk
ms.assetid: 5369566b-fa64-4aec-ad3e-1a129bcefdd6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_p_to_z_cedf94f0-1f4a-46cf-aa81-914ab30d2a98.xml, FltUnregisterFilter, FltUnregisterFilter function [Installable File System Drivers], fltkernel/FltUnregisterFilter, ifsk.fltunregisterfilter
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltUnregisterFilter
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltUnregisterFilter function


## -description


A registered minifilter driver calls <b>FltUnregisterFilter</b> to unregister itself so that the Filter Manager no longer calls it to process I/O operations. 


## -parameters




### -param Filter [in]

Opaque filter pointer returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>. 


## -returns



None 




## -remarks



<b>FltUnregisterFilter</b> unregisters the minifilter driver's callback routines and removes any contexts that the minifilter driver has set on files, volumes, instances, streams, or stream handles. It also calls the minifilter driver's <i>InstanceTeardownStartCallback</i> and <i>InstanceTeardownCompleteCallback</i> (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551098">PFLT_INSTANCE_TEARDOWN_CALLBACK</a>) routines for each minifilter driver instance. 

A minifilter driver typically calls <b>FltUnregisterFilter</b> from its unload routine when it is about to be unloaded. 

A minifilter driver can only call <b>FltUnregisterFilter</b> to unregister itself, not another minifilter driver. 

To register a minifilter driver, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544811">FLT_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551085">PFLT_FILTER_UNLOAD_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551098">PFLT_INSTANCE_TEARDOWN_CALLBACK</a>
 

 

