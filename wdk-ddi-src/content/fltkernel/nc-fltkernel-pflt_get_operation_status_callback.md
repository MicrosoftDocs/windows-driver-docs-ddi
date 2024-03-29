---
UID: NC:fltkernel.PFLT_GET_OPERATION_STATUS_CALLBACK
title: PFLT_GET_OPERATION_STATUS_CALLBACK (fltkernel.h)
description: A minifilter driver can register a routine of type PFLT_GET_OPERATION_STATUS_CALLBACK as the minifilter driver's OperationStatusCallback routine.
old-location: ifsk\PFLT_GET_OPERATION_STATUS_CALLBACK.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["PFLT_GET_OPERATION_STATUS_CALLBACK callback function"]
ms.keywords: OperationStatusCallback, OperationStatusCallback routine [Installable File System Drivers], PFLT_GET_OPERATION_STATUS_CALLBACK, fltkernel/OperationStatusCallback, ifsk.PFLT_GET_OPERATION_STATUS_CALLBACK
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PFLT_GET_OPERATION_STATUS_CALLBACK
 - fltkernel/PFLT_GET_OPERATION_STATUS_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - FltKernel.h
api_name:
 - PFLT_GET_OPERATION_STATUS_CALLBACK
---

# PFLT_GET_OPERATION_STATUS_CALLBACK callback function


## -description

A minifilter driver can register a routine of type <i>PFLT_GET_OPERATION_STATUS_CALLBACK</i> as the minifilter driver's OperationStatusCallback routine.

## -parameters

### -param FltObjects [in]


A pointer to an <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a> structure that contains opaque pointers for the objects related to the current operation.

### -param IopbSnapshot [in]


A pointer to the data structure containing parameters from the IO Request Packet for the operation.

### -param OperationStatus [in]


The NTSTATUS value of the I/O operation generating the callback.

### -param RequesterContext [in, optional]


An optional pointer to a minifilter driver-provided context information of the requester passed from <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltrequestoperationstatuscallback">FltRequestOperationStatusCallback</a>.

## -remarks

A minifilter driver can register a routine of type <i>PFLT_GET_OPERATION_STATUS_CALLBACK</i> as the minifilter driver's OperationStatusCallback routine. 



Most minifilter drivers never need to register a routine of type <i>PFLT_GET_OPERATION_STATUS_CALLBACK</i>. Normally, a minifilter driver only calls this routine to determine whether a requested opportunistic lock was granted.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_io_parameter_block">FLT_IO_PARAMETER_BLOCK</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltrequestoperationstatuscallback">FltRequestOperationStatusCallback</a>

