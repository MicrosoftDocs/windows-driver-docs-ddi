---
UID: NS:wdm._NAMED_PIPE_CREATE_PARAMETERS
title: _NAMED_PIPE_CREATE_PARAMETERS (wdm.h)
description: The NAMED_PIPE_CREATE_PARAMETERS structure is used by the Windows subsystem to create a named pipe.
tech.root: ifsk
ms.assetid: 2db2ba80-17c2-4161-9be7-c3fdc8d824cd
ms.date: 10/30/2019
ms.keywords: "*PNAMED_PIPE_CREATE_PARAMETERS, NAMED_PIPE_CREATE_PARAMETERS, NAMED_PIPE_CREATE_PARAMETERS structure"
ms.topic: struct
f1_keywords:
 - "wdm/NAMED_PIPE_CREATE_PARAMETERS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- NAMED_PIPE_CREATE_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NAMED_PIPE_CREATE_PARAMETERS, *PNAMED_PIPE_CREATE_PARAMETERS
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

For an [IRP_MJ_CREATE_NAMED_PIPE](https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create-named-pipe) operation, [FLT_PARAMETERS](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_parameters) is a *CreatePipe* structure, and *CreatePipe.Parameters* points to a NAMED_PIPE_CREATE_PARAMETERS structure that describes the named pipe to create or open.

## -see-also

[FLT_PARAMETERS](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_parameters)
## -see-also

[IRP_MJ_CREATE_NAMED_PIPE](https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create-named-pipe)
