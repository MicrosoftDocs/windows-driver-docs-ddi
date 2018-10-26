---
UID: NC:fltkernel.PFLT_NORMALIZE_CONTEXT_CLEANUP
title: PFLT_NORMALIZE_CONTEXT_CLEANUP
author: windows-driver-content
description: A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_CONTEXT_CLEANUP as the minifilter driver's NormalizeContextCleanupCallback routine.
old-location: ifsk\pflt_normalize_context_cleanup.htm
tech.root: ifsk
ms.assetid: 968cfc99-4862-41f7-bf7e-d579a3e8061f
ms.date: 04/16/2018
ms.keywords: FltCallbacks_3391a3bd-55a2-4f87-b116-78c2e4f93b88.xml, NormalizeContextCleanupCallback, NormalizeContextCleanupCallback routine [Installable File System Drivers], PFLT_NORMALIZE_CONTEXT_CLEANUP, fltkernel/NormalizeContextCleanupCallback, ifsk.pflt_normalize_context_cleanup
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
-	NormalizeContextCleanupCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFLT_NORMALIZE_CONTEXT_CLEANUP callback function


## -description


A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_CONTEXT_CLEANUP as the minifilter driver's <i>NormalizeContextCleanupCallback</i> routine. 


## -parameters




### -param *NormalizationContext [in, optional]

Pointer to minifilter driver-provided context information to be passed in any calls to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551102">PFLT_NORMALIZE_NAME_COMPONENT</a> callback routine that are made to normalize multiple components in the same file name path. 


## -returns



None. 




## -remarks



A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_CONTEXT_CLEANUP as the minifilter driver's <i>NormalizeContextCleanupCallback</i> routine. 

To register this callback routine, the minifilter driver stores the address of a routine of type PFLT_NORMALIZE_CONTEXT_CLEANUP in the <b>NormalizeContextCleanupCallback</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544811">FLT_REGISTRATION</a> structure that the minifilter driver passes as a parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>. 

The filter manager calls this callback routine to allow the minifilter driver to perform any needed cleanup for the context information passed in the <i>NormalizationContext</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551102">PFLT_NORMALIZE_NAME_COMPONENT</a> callback routine. This context is set by the minifilter driver when its PFLT_NORMALIZE_NAME_COMPONENT callback routine is called. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544811">FLT_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544305">FltRegisterFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551087">PFLT_GENERATE_FILE_NAME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551102">PFLT_NORMALIZE_NAME_COMPONENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551105">PFLT_NORMALIZE_NAME_COMPONENT_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

