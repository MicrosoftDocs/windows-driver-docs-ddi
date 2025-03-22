---
UID: NC:prminterface.PRM_INVOKE_HANDLER
tech.root: kernel
title: PRM_INVOKE_HANDLER
ms.date: 02/05/2024
targetos: Windows
description: "Invokes a specific PRM handler"
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: prminterface.h
req.idl: 
req.include-header: 
req.irql: <= HIGH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - prminterface.h
api_name:
 - PRM_INVOKE_HANDLER
f1_keywords:
 - PRM_INVOKE_HANDLER
 - prminterface/PRM_INVOKE_HANDLER
dev_langs:
 - c++
helpviewer_keywords:
 - PRM_INVOKE_HANDLER
---

# PRM_INVOKE_HANDLER function (prminterface.h)

## -description

This routine invokes a specific PRM handler.

## -parameters

### -param HandlerGuid [in]

Pointer to a 128-bit unique identifier that specifies the PRM handler to invoke.

### -param ParameterBuffer [in]

Pointer to a caller-allocated PRM handler parameter buffer.

### -param Reserved [in]

Reserved. Set to zero.

### -param EfiStatus [out]

Pointer to a ULONG64 which, on output, contains the EFI status from the PRM handler invocation.

## -returns

This method returns NTSTATUS which contains STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

PRM_INVOKE_HANDLER is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a [PRM_INTERFACE](./ns-prminterface-prm_interface.md) structure. Drivers obtain the address of this routine by calling [**ExGetPrmInterface**](./nf-prminterface-exgetprminterface.md).

## -see-also

[Windows Kernel-Mode PRM Library](/windows-hardware/drivers/kernel/windows-kernel-mode-prm-library)