---
UID: NC:d3dkmddi.DXGKDDI_CREATEPROCESS
title: DXGKDDI_CREATEPROCESS (d3dkmddi.h)
description: DxgkDdiCreateProcess creates a graphics kernel process object.
ms.date: 02/03/2025
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
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
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_CREATEPROCESS
 - d3dkmddi/DXGKDDI_CREATEPROCESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
 - d3dkmddi.h
api_name:
 - DXGKDDI_CREATEPROCESS
---

# DXGKDDI_CREATEPROCESS callback function

## -description

*Dxgkrnl* calls the kernel-mode display driver's (KMD) **DxgkDdiCreateProcess** function to create a kernel-mode driver (KMD) process object for a *Dxgkrnl* process object.

## -parameters

### -param hAdapter

[in] A handle to the display adapter.

### -param pArgs

[in/out] Pointer to a [**DXGKARG_CREATEPROCESS**](ns-d3dkmddi-_dxgkarg_createprocess.md) structure that describes the operation.

## -returns

**DxgkDdiCreateProcess** returns STATUS_SUCCESS if it succeeds. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

**DxgkDdiCreateProcess** allows the KMD to create a process context that allows the KMD to manage resources and permissions for processes, including those running in specialized environments like virtual machines and containers, ensuring proper graphics operations across different system contexts.

During process creation, the kernel-mode driver is allowed to call the [**DxgkCbReserveVirtualAddressRange**](nc-d3dkmddi-dxgkcb_reservegpuvirtualaddressrange.md) callback. At this point the GPU virtual address space for the process is free and the driver has the opportunity to reserve virtual address space for its needs.

When [**CREATEPROCESSFLAGS::VirtualMachineWorkerProcess**](ns-d3dkmddi-_dxgk_createprocessflags.md) is set, the process belongs to the worker process of a virtual machine.

## -see-also

[**DXGKARG_CREATEPROCESS**](ns-d3dkmddi-_dxgkarg_createprocess)
