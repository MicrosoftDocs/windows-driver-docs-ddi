---
UID: NC:d3dkmddi.DXGKDDI_CREATECPUEVENT
tech.root: display
title: DXGKDDI_CREATECPUEVENT
ms.date: 09/12/2022
targetos: Windows
description: Learn more about the DXGKDDI_CREATECPUEVENT function.
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
 - DXGKDDI_CREATECPUEVENT
f1_keywords:
 - DXGKDDI_CREATECPUEVENT
 - d3dkmddi/DXGKDDI_CREATECPUEVENT
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_CREATECPUEVENT
---

## -description

**DXGKDDI_CREATECPUEVENT** creates the kernel-mode driver's (KMD's) CPU event object for the corresponding *Dxgkrnl* object.

## -parameters

### -param hAdapter

[in] Handle to a KMD context that is associated with a display adapter. The display miniport driver previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DXGKDDI_ADD_DEVICE**](/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device) function.

### -param pArgs

[in/out] Pointer to a [**DXGKARG_CREATECPUEVENT**](/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-dxgkarg_createcpuevent) structure with additional parameters.

## -returns

**DXGKDDI_CREATECPUEVENT** returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in *Ntstatus.h*.

## -remarks

KMD CPU event sync objects are linked with a device object (**hKmdDevice**). When a device object is destroyed, *Dxgkrnl* will destroy all associated KMD CPU event sync objects by calling [**DXGKDDI_DESTROYCPUEVENT**](nc-d3dkmddi-dxgkddi_destroycpuevent.md).

KMD can signal the event by calling [**DXGKCB_SIGNALEVENT**](/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_signalevent) and providing the **hDxgCpuEvent** handle.

The CPU event object lifetime does not depend on KMD's device lifetime; that is, the object could be destroyed after the device is destroyed. **hKmdDevice** is passed so the driver can associate the KMD process objects (created by [**DXGKDDI_CREATEPROCESS**](nc-d3dkmddi-dxgkddi_createprocess.md)) with the CPU event object.

See [Signaling a CPU event from KMD](/windows-hardware/drivers/display/signaling-cpu-event-from-kmd) for more information.

## -see-also

[**DXGKARG_CREATECPUEVENT**](/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-dxgkarg_createcpuevent)

[**DXGKDDI_DESTROYCPUEVENT**](nc-d3dkmddi-dxgkddi_destroycpuevent.md)
