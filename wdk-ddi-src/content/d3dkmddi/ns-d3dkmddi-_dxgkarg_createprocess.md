---
UID: NS:d3dkmddi._DXGKARG_CREATEPROCESS
title: DXGKARG_CREATEPROCESS (d3dkmddi.h)
description: DXGKARG_CREATEPROCESS is used with DxgkDdiCreateProcess to create a kernel mode driver object for a Microsoft DirectX graphics kernel process object.
ms.date: 02/06/2025
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
targetos: Windows
tech.root: display
req.typenames: DXGKARG_CREATEPROCESS
f1_keywords:
 - _DXGKARG_CREATEPROCESS
 - d3dkmddi/_DXGKARG_CREATEPROCESS
 - DXGKARG_CREATEPROCESS
 - d3dkmddi/DXGKARG_CREATEPROCESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_CREATEPROCESS
 - DXGKARG_CREATEPROCESS
---

# DXGKARG_CREATEPROCESS structure

## -description

**DXGKARG_CREATEPROCESS** is used with [**DxgkDdiCreateProcess**](nc-d3dkmddi-dxgkddi_createprocess.md) to create a kernel-mode driver (KMD) process object for a *Dxgkrnl* process object.

## -struct-fields

### -field hDxgkProcess [in]

The handle to the *Dxgkrnl* process (DXGPROCESS).

### -field hKmdProcess [out]

Output handle to the process object created by the KMD.

### -field Flags [in]

A [**DXGK_CREATEPROCESSFLAGS**](ns-d3dkmddi-_dxgk_createprocessflags.md) structure describing the process creation operation.

### -field NumPasid [in]

The number of elements in the process address space identifier array located in the **pPasid**  member.

### -field pPasid [in]

A pointer to an array of process address identifiers. There is one identifier for each of the physical GPUs.

### -field hKmdVmWorkerProcess [in]

Handle of the driver VM worker process returned by the system when you create a process with [**VirtualMachineWorkerProcess**](ns-d3dkmddi-_dxgk_createprocessflags.md) set. This value is valid only when **VirtualMachineProcess** is set.

### -field ProcessNameLength [in]

The number of Unicode characters in the array that **pProcessName** points to, not including the terminating NULL.

### -field pProcessName [in]

Pointer to a NULL-terminated Unicode string that contains the process name. When **VirtualMachineProcess** is set, this string is the name of the process inside a virtual machine. Can be NULL.

## -see-also

[**DXGK_CREATEPROCESSFLAGS**](ns-d3dkmddi-_dxgk_createprocessflags.md)

[**DxgkDdiCreateProcess**](nc-d3dkmddi-dxgkddi_createprocess.md)
