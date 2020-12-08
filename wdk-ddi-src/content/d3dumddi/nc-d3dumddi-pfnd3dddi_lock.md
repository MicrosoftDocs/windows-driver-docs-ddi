---
UID: NC:d3dumddi.PFND3DDDI_LOCK
title: PFND3DDDI_LOCK (d3dumddi.h)
description: The Lock function locks the given resource or a surface within the resource.
old-location: display\lock.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_LOCK callback function"]
ms.keywords: Lock, Lock callback function [Display Devices], PFND3DDDI_LOCK, PFND3DDDI_LOCK callback, UserModeDisplayDriver_Functions_c4db91e8-a67e-4647-97d3-abde07926169.xml, d3dumddi/Lock, display.lock
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFND3DDDI_LOCK
 - d3dumddi/PFND3DDDI_LOCK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - Lock
product:
 - Windows
---

# PFND3DDDI_LOCK callback function


## -description

The <i>Lock</i> function locks the given resource or a surface within the resource.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_lock">D3DDDIARG_LOCK</a> structure that describes the resource or surface within the resource to lock.

## -returns

<i>Lock</i> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The resource is successfully locked. | 
| **E_OUTOFMEMORY** | Lock could not allocate the required memory for it to complete. | 
| **D3DDDIERR_WASSTILLDRAWING** | The resource was not idle when the Microsoft Direct3D runtime called the Lock function with the DoNotWait bit-field flag set in the Flags member of [D3DDDIARG_LOCK](./ns-d3dumddi-_d3dddiarg_lock.md) . |

## -remarks

The Microsoft Direct3D runtime calls the user-mode display driver's <i>Lock</i> function to lock a resource or a surface within the resource. This locked resource or surface can be read from or written to by using read and write operations from the CPU. When the runtime calls <i>Lock</i>, the user-mode display driver must call the runtime's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a> callback function to lock an allocation corresponding to the resource or surface. Note that because the user-mode display driver can allocate multiple allocations for each resource or surface, the user-mode display driver might be required to appropriately convert or process the allocation pointer that is returned from <b>pfnLockCb</b> before returning the <i>Lock</i> call to the runtime. 

Typically, calls to <i>Lock</i> are followed by matching calls to the driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_unlock">Unlock</a> function before the driver receives any calls to its draw-primitive functions (that is, calls to <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_drawindexedprimitive">DrawIndexedPrimitive</a>, <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_drawindexedprimitive2">DrawIndexedPrimitive2</a>, <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_drawprimitive">DrawPrimitive</a>, and <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_drawprimitive2">DrawPrimitive2</a>). This order guarantees that a driver is never requested to draw from a locked resource. However, on occasion, when performing software transform and lighting, the runtime must call one of the driver's draw-primitive functions before unlocking a resource (currently, only vertex buffers exhibit this behavior). The runtime marks vertex buffers on which this uncommon behavior might occur with the <b>MightDrawFromLocked</b> bit-field flag in the <b>Flags</b> member of the <a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddiarg_createresource">D3DDDIARG_CREATERESOURCE</a> and <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_lock">D3DDDIARG_LOCK</a> structures (that is, both at creation and at lock time). When the hardware actively renders from a locked vertex buffer, the driver is not required to take any special action because the runtime will not overwrite any data in the locked vertex buffer . 

The runtime calls the user-mode display driver's <i>Lock</i> function to lock preallocated system memory surfaces as well. This operation allows the user-mode display driver to properly synchronize references to such surfaces that might be in the hardware command stream. The user-mode display driver can accomplish the synchronization by: 

<ul>
<li>
Flushing (that is, calling the runtime's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a> callback function) any outstanding commands as necessary.

</li>
<li>
Calling <b>pfnLockCb</b> with the appropriate allocation handle for commands that have already been submitted to hardware. 

</li>
</ul>
The user-mode display driver returns a pointer to the memory for the locked surface and the pitch of the surface in the <b>pSurfData</b> and <b>Pitch</b> members of the D3DDDIARG_LOCK structure. However, for preallocated system memory surfaces, the runtime ignores the driver-set memory and pitch, although the driver can still fail the <i>Lock</i> call (and thus fail back to the application). The runtime sets the <b>NotifyOnly</b> bit-field flag in the <b>Flags</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_lock">D3DDDIARG_LOCK</a> structure to differentiate <i>Lock</i> calls that lock preallocated system memory surfaces from other <i>Lock</i> calls.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_lock">D3DDDIARG_LOCK</a>



<a href="/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_allocationinfo">D3DDDI_ALLOCATIONINFO</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a>
