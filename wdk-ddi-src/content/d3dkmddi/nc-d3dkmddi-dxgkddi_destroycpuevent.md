---
UID: NC:d3dkmddi.DXGKDDI_DESTROYCPUEVENT
tech.root: display
title: DXGKDDI_DESTROYCPUEVENT
ms.date: 09/12/2022
targetos: Windows
description: Learn more about the DXGKDDI_DESTROYCPUEVENT function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11 version 21H2 (WDDM 3.0)
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
 - DXGKDDI_DESTROYCPUEVENT
f1_keywords:
 - DXGKDDI_DESTROYCPUEVENT
 - d3dkmddi/DXGKDDI_DESTROYCPUEVENT
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_DESTROYCPUEVENT
---

## -description

**DXGKDDI_DESTROYCPUEVENT** destroys the specified kernel-mode driver (KMD) CPU object.

## -parameters

### -param hAdapter

[in] Handle to a KMD context that is associated with a display adapter. The display miniport driver previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DXGKDDI_ADD_DEVICE**](/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device) function.

### -param hKmdCpuEvent

[in] KMD CPU event object handle, which was returned by KMD from [**DXGKDDI_CREATECPUEVENT**](nc-d3dkmddi-dxgkddi_createcpuevent.md).

## -returns

**DXGKDDI_DESTROYCPUEVENT** returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

The *Dxgkrnl* CPU event object cannot be used after this DDI is called. The driver must synchronize destruction with all calls to [**DXGKCB_SIGNALEVENT**](/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_signalevent).

It is guaranteed that the OS will call this DDI to destroy KMD sync objects. Objects could be destroyed when a user-mode client destroys a sync object, when a process terminates, or when the adapter is stopped.

See [Signaling a CPU event from KMD](/windows-hardware/drivers/display/signaling-cpu-event-from-kmd) for more information.

## -see-also

[**DXGKDDI_CREATECPUEVENT**](nc-d3dkmddi-dxgkddi_createcpuevent.md)
