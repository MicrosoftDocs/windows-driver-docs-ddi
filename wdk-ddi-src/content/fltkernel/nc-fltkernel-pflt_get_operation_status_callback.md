---
UID: NC:fltkernel.PFLT_GET_OPERATION_STATUS_CALLBACK
title: PFLT_GET_OPERATION_STATUS_CALLBACK
author: windows-driver-content
description: A minifilter driver can register a routine of type PFLT_GET_OPERATION_STATUS_CALLBACK as the minifilter driver's OperationStatusCallback routine.
old-location: ifsk\PFLT_GET_OPERATION_STATUS_CALLBACK.htm
old-project: ifsk
ms.assetid: f3fedf69-260c-4117-b302-db3ce6b182a0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.PFLT_GET_OPERATION_STATUS_CALLBACK, OperationStatusCallback routine [Installable File System Drivers], OperationStatusCallback, PFLT_GET_OPERATION_STATUS_CALLBACK, PFLT_GET_OPERATION_STATUS_CALLBACK, fltkernel/OperationStatusCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later operating systems. Not available in Windows 2000 SP4 and earlier operating systems.
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	FltKernel.h
apiname:
-	OperationStatusCallback
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# PFLT_GET_OPERATION_STATUS_CALLBACK callback


## -description


A minifilter driver can register a routine of type <i>PFLT_GET_OPERATION_STATUS_CALLBACK</i> as the minifilter driver's OperationStatusCallback routine.




## -prototype


````
PFLT_GET_OPERATION_STATUS_CALLBACK OperationStatusCallback;

VOID OperationStatusCallback(
  _In_     PCFLT_RELATED_OBJECTS   FltObjects,
  _In_     PFLT_IO_PARAMETER_BLOCK IopbSnapshot,
  _In_     NTSTATUS                OperationStatus,
  _In_opt_ PVOID                   RequesterContext
)
{ ... }
````


## -parameters




#### - FltObjects [in]

A pointer to an <a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a> structure that contains opaque pointers for the objects related to the current operation.


#### - IopbSnapshot [in]

A pointer to the data structure containing parameters from the IO Request Packet for the operation. 


#### - OperationStatus [in]

The NTSTATUS value of the I/O operation generating the callback. 


#### - RequesterContext [in, optional]

An optional pointer to a minifilter driver-provided context information of the requester passed from <a href="..\fltkernel\nf-fltkernel-fltrequestoperationstatuscallback.md">FltRequestOperationStatusCallback</a>. 


## -returns


This routine does not return a value.



## -remarks


A minifilter driver can register a routine of type <i>PFLT_GET_OPERATION_STATUS_CALLBACK</i> as the minifilter driver's OperationStatusCallback routine. 



Most minifilter drivers never need to register a routine of type <i>PFLT_GET_OPERATION_STATUS_CALLBACK</i>. Normally, a minifilter driver only calls this routine to determine whether a requested opportunistic lock was granted. 




## -see-also

<a href="..\fltkernel\ns-fltkernel-_flt_io_parameter_block.md">FLT_IO_PARAMETER_BLOCK</a>

<a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a>

<a href="..\fltkernel\nf-fltkernel-fltrequestoperationstatuscallback.md">FltRequestOperationStatusCallback</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PFLT_GET_OPERATION_STATUS_CALLBACK routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

