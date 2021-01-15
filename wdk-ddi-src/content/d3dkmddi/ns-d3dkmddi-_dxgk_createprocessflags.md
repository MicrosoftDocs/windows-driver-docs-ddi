---
UID: NS:d3dkmddi._DXGK_CREATEPROCESSFLAGS
title: _DXGK_CREATEPROCESSFLAGS (d3dkmddi.h)
description: DXGK_CREATEPROCESSFLAGS is used with DXGKARG_CREATEPROCESS and DxgkDdiCreateProcess to create a kernel mode driver object for a Microsoft DirectX graphics kernel process object.
old-location: display\dxgk_createprocessflags.htm
ms.date: 05/10/2018
keywords: ["DXGK_CREATEPROCESSFLAGS structure"]
ms.keywords: DXGK_CREATEPROCESSFLAGS, DXGK_CREATEPROCESSFLAGS structure [Display Devices], _DXGK_CREATEPROCESSFLAGS, d3dkmddi/DXGK_CREATEPROCESSFLAGS, display.dxgk_createprocessflags
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

# _DXGK_CREATEPROCESSFLAGS structure


## -description

<b>DXGK_CREATEPROCESSFLAGS</b> is used with <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createprocess">DXGKARG_CREATEPROCESS</a> and <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createprocess">DxgkDdiCreateProcess</a> to create a kernel mode driver object for a Microsoft DirectX graphics kernel process object.

## -struct-fields

### -field SystemProcess

Indicates that a system process is being created.

### -field GdiProcess

Indicates that a GDI process is being created.

### -field VirtualMachineProcess

The virtual machine DXG process created during a call to DxgkDdiCreateProcess. Note that each virtual machine DXG process will belong to the same EPROCESS as the same virtual machine worker process.

### -field VirtualMachineWorkerProcess

The virtual machine worker process created during a call to DxgkDdiCreateProcess. Note that because no rendering or driver resource is created in this process context, the driver might skip allocating certain resources.

### -field SessionIsolatedContainer

The session isolated container.

### -field Reserved

This member is reserved and should be set to zero.

### -field Value

The consolidated value of the bitfield members of the structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createprocess">DXGKARG_CREATEPROCESS</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createprocess">DxgkDdiCreateProcess</a>

