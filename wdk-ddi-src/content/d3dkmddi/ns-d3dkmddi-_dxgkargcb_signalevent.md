---
UID: NS:d3dkmddi._DXGKARGCB_SIGNALEVENT
title: _DXGKARGCB_SIGNALEVENT (d3dkmddi.h)
description: Arguments used in the call to DXGKCB_SIGNALEVENT.
ms.assetid: 07a8e812-e56f-4ff6-afe0-77c38103b08b
ms.date: 10/19/2018
keywords: ["DXGKARGCB_SIGNALEVENT structure"]
ms.keywords: _DXGKARGCB_SIGNALEVENT, DXGKARGCB_SIGNALEVENT,
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKARGCB_SIGNALEVENT
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - _DXGKARGCB_SIGNALEVENT
 - d3dkmddi/_DXGKARGCB_SIGNALEVENT
 - DXGKARGCB_SIGNALEVENT
 - d3dkmddi/DXGKARGCB_SIGNALEVENT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_SIGNALEVENT
dev_langs:
 - c++
---

# _DXGKARGCB_SIGNALEVENT structure


## -description

Arguments used in the call to [DXGKCB_SIGNALEVENT](nc-d3dkmddi-dxgkcb_signalevent.md).

## -struct-fields

### -field hDxgkProcess

Handle to the DXG process object, which is passed to [DxgkDdiCreateProcess](nc-d3dkmddi-dxgkddi_createprocess.md). The process must be created for a virtual machine, where DXGK_CREATEPROCESSFLAGS::VirtualMachineProcess is set in DxgkDdiCreateProcess.

The driver must synchronize the callback with [DxgkDdiDestroyProcess](nc-d3dkmddi-dxgkddi_destroyprocess.md) to ensure that the process is not destroyed during the callback.

### -field hEvent

User mode event handle, which needs to be signaled. The handle is valid in the context of the DXG process, identified by *hDxgkProcess*. The user mode driver in the guest could send the user mode event handle to kernel mode driver via [DXGKDDI_ESCAPE](nc-d3dkmddi-dxgkddi_escape.md) or other APIs, which allow private driver data.

### -field Reserved

Reserved. Should be zero.

### -field Flags

 
The driver must call the callback with the *LastUse* flag during process or device cleanup.

## -remarks

## -see-also

