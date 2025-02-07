---
UID: NS:d3dkmddi._DXGK_CREATEPROCESSFLAGS
title: DXGK_CREATEPROCESSFLAGS (d3dkmddi.h)
description: DXGK_CREATEPROCESSFLAGS is used with DXGKARG_CREATEPROCESS and DxgkDdiCreateProcess to create a kernel mode driver object for a Microsoft DirectX graphics kernel process object.
ms.date: 02/03/2025
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
req.irql:
targetos: Windows
tech.root: display
req.typenames: DXGK_CREATEPROCESSFLAGS
f1_keywords:
 - _DXGK_CREATEPROCESSFLAGS
 - d3dkmddi/_DXGK_CREATEPROCESSFLAGS
 - DXGK_CREATEPROCESSFLAGS
 - d3dkmddi/DXGK_CREATEPROCESSFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_CREATEPROCESSFLAGS
 - DXGK_CREATEPROCESSFLAGS
---

# DXGK_CREATEPROCESSFLAGS structure

## -description

**DXGK_CREATEPROCESSFLAGS** are *Dxgkrnl*-provided flags that describe the characteristics of *Dxgkrnl*'s process that [**DxgkDdiCreateProcess**](nc-d3dkmddi-dxgkddi_createprocess.md) is to create a kernel-mode driver (KMD) process object for.

## -struct-fields

### -field SystemProcess

Indicates that the process referenced by [**hDxgkProcess**](ns-d3dkmddi-_dxgkarg_createprocess.md) is a system process.

### -field GdiProcess

Indicates that the process referenced by [**hDxgkProcess**](ns-d3dkmddi-_dxgkarg_createprocess.md) is a GDI process.

### -field VirtualMachineProcess

Indicates that the *Dxgkrnl* process being created during a call to [**DxgkDdiCreateProcess**](nc-d3dkmddi-dxgkddi_createprocess.md) is associated with a virtual machine. Each virtual machine *Dxgkrnl* process will belong to the same EPROCESS as the same virtual machine worker process. Introduced in WDDM 2.2.

### -field VirtualMachineWorkerProcess

Indicates that the process being created during a call to [**DxgkDdiCreateProcess**](nc-d3dkmddi-dxgkddi_createprocess.md) is the worker process for a virtual machine. Because no rendering or driver resource is created in this process context, the driver might skip allocating certain resources. Introduced in WDDM 2.4.

### -field SessionIsolatedContainer

Indicates whether the process is running within a session-isolated container. Introduced in WDDM 2.5.

### -field Reserved

This member is reserved and should be set to zero.

### -field Value

The consolidated value of the bitfield members of the structure.

## -see-also

[**DXGKARG_CREATEPROCESS**](ns-d3dkmddi-_dxgkarg_createprocess.md)

[**DxgkDdiCreateProcess**](nc-d3dkmddi-dxgkddi_createprocess.md)
