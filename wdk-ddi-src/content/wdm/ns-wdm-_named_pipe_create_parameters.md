---
UID: NS:wdm._NAMED_PIPE_CREATE_PARAMETERS
title: _NAMED_PIPE_CREATE_PARAMETERS (wdm.h)
description: The NAMED_PIPE_CREATE_PARAMETERS structure is used by the Windows subsystem to create a named pipe.
tech.root: kernel
ms.date: 11/06/2019
keywords: ["NAMED_PIPE_CREATE_PARAMETERS structure"]
ms.keywords: "*PNAMED_PIPE_CREATE_PARAMETERS, NAMED_PIPE_CREATE_PARAMETERS, NAMED_PIPE_CREATE_PARAMETERS structure"
req.header: wdm.h
req.include-header: Ntifs.h
req.target-type: Windows
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
req.irql: 
targetos: Windows
req.typenames: NAMED_PIPE_CREATE_PARAMETERS, *PNAMED_PIPE_CREATE_PARAMETERS
f1_keywords:
 - _NAMED_PIPE_CREATE_PARAMETERS
 - wdm/_NAMED_PIPE_CREATE_PARAMETERS
 - PNAMED_PIPE_CREATE_PARAMETERS
 - wdm/PNAMED_PIPE_CREATE_PARAMETERS
 - NAMED_PIPE_CREATE_PARAMETERS
 - wdm/NAMED_PIPE_CREATE_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _NAMED_PIPE_CREATE_PARAMETERS
 - PNAMED_PIPE_CREATE_PARAMETERS
 - NAMED_PIPE_CREATE_PARAMETERS
---

# _NAMED_PIPE_CREATE_PARAMETERS structure


## -description

 The NAMED_PIPE_CREATE_PARAMETERS structure is used by the Windows subsystem to create a named pipe.

## -struct-fields

### -field NamedPipeType

Type of named pipe to create.

### -field ReadMode

Mode in which to read the pipe.

### -field CompletionMode

Specifies how the operation is to be completed.

### -field MaximumInstances

Maximum number of simultaneous instances of the named pipe.

### -field InboundQuota

Pool quota that is reserved for writes to the inbound side of the named pipe.

### -field OutboundQuota

Pool quota that is reserved for writes to the outbound side of the named pipe.

### -field DefaultTimeout

Pointer to a timeout value to use if a timeout value is not specified when waiting for an instance of a named pipe. This member is optional and can be set to **NULL**.

### -field TimeoutSpecified

Boolean value that specifies whether a pointer to a timeout period was provided in the *DefaultTimeout* member.

## - remarks

For an [IRP_MJ_CREATE_NAMED_PIPE](/windows-hardware/drivers/ifs/irp-mj-create-named-pipe) operation, [FLT_PARAMETERS](../fltkernel/ns-fltkernel-_flt_parameters.md) is a *CreatePipe* structure, and *CreatePipe.Parameters* points to a NAMED_PIPE_CREATE_PARAMETERS structure that describes the named pipe to create or open.

## -see-also

[FLT_PARAMETERS](../fltkernel/ns-fltkernel-_flt_parameters.md)

