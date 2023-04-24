---
UID: NC:d3dkmddi.DXGKDDI_SETINTERRUPTTARGETPRESENTID
tech.root: display
title: DXGKDDI_SETINTERRUPTTARGETPRESENTID
ms.date: 02/03/2023
targetos: Windows
description: Learn more about the DXGKDDI_SETINTERRUPTTARGETPRESENTID callback function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: DIRQL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
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
 - d3dkmddi.h
api_name:
 - DXGKDDI_SETINTERRUPTTARGETPRESENTID
f1_keywords:
 - DXGKDDI_SETINTERRUPTTARGETPRESENTID
 - d3dkmddi/DXGKDDI_SETINTERRUPTTARGETPRESENTID
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_SETINTERRUPTTARGETPRESENTID
---

## -description

The OS calls a display driver's **DXGKDDI_SETINTERRUPTTARGETPRESENTID** function to specify the target PresentId that should result in a Vsync interrupt being raised when the corresponding flip is completed.

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the **MiniportDeviceContext** output parameter of the [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pSetInterruptTargetPresentId

[in] Pointer to a [**DXGKARG_SETINTERRUPTTARGETPRESENTID**](ns-d3dkmddi-dxgkarg_setinterrupttargetpresentid.md) structure containing the parameters for this function.

## -returns

**DXGKDDI_SETINTERRUPTTARGETPRESENTID** returns STATUS_SUCCESS. The driver should always return a success code.

## -remarks

**DXGKDDI_SETINTERRUPTTARGETPRESENTID** is called at the device interrupt level to synchronize with [**DXGKDDI_SETVIDPNSOURCEADDRESS**](nc-d3dkmddi-dxgkddi_setvidpnsourceaddress.md) and the VSync interrupt.

See [Specifying Vsync interrupt behavior](/windows-hardware/drivers/display/hardware-flip-queue#specifying-vsync-interrupt-behavior) for more information.

## -see-also

[**DXGKARG_SETINTERRUPTTARGETPRESENTID**](ns-d3dkmddi-dxgkarg_setinterrupttargetpresentid.md)
