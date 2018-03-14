---
UID: NC:d3dumddi.PFND3DDDI_LOCK
title: PFND3DDDI_LOCK
author: windows-driver-content
description: The Lock function locks the given resource or a surface within the resource.
old-location: display\lock.htm
old-project: display
ms.assetid: e2289073-d46a-4a12-8de7-30400e04cc22
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Lock, Lock callback function [Display Devices], PFND3DDDI_LOCK, UserModeDisplayDriver_Functions_c4db91e8-a67e-4647-97d3-abde07926169.xml, d3dumddi/Lock, display.lock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	Lock
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_LOCK callback


## -description


The <i>Lock</i> function locks the given resource or a surface within the resource. 


## -prototype


````
PFND3DDDI_LOCK Lock;

__checkReturn HRESULT APIENTRY Lock(
  _In_    HANDLE         hDevice,
  _Inout_ D3DDDIARG_LOCK *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_lock.md">D3DDDIARG_LOCK</a> structure that describes the resource or surface within the resource to lock.


## -returns



<i>Lock</i> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The resource is successfully locked.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>Lock</i> could not allocate the required memory for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_WASSTILLDRAWING</b></dt>
</dl>
</td>
<td width="60%">
The resource was not idle when the Microsoft Direct3D runtime called the <i>Lock</i> function with the <b>DoNotWait</b> bit-field flag set in the <b>Flags</b> member of <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_lock.md">D3DDDIARG_LOCK</a>.

</td>
</tr>
</table>
 




## -remarks



The Microsoft Direct3D runtime calls the user-mode display driver's <i>Lock</i> function to lock a resource or a surface within the resource. This locked resource or surface can be read from or written to by using read and write operations from the CPU. When the runtime calls <i>Lock</i>, the user-mode display driver must call the runtime's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a> callback function to lock an allocation corresponding to the resource or surface. Note that because the user-mode display driver can allocate multiple allocations for each resource or surface, the user-mode display driver might be required to appropriately convert or process the allocation pointer that is returned from <b>pfnLockCb</b> before returning the <i>Lock</i> call to the runtime. 

Typically, calls to <i>Lock</i> are followed by matching calls to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlock.md">Unlock</a> function before the driver receives any calls to its draw-primitive functions (that is, calls to <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawindexedprimitive.md">DrawIndexedPrimitive</a>, <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawindexedprimitive2.md">DrawIndexedPrimitive2</a>, <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawprimitive.md">DrawPrimitive</a>, and <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawprimitive2.md">DrawPrimitive2</a>). This order guarantees that a driver is never requested to draw from a locked resource. However, on occasion, when performing software transform and lighting, the runtime must call one of the driver's draw-primitive functions before unlocking a resource (currently, only vertex buffers exhibit this behavior). The runtime marks vertex buffers on which this uncommon behavior might occur with the <b>MightDrawFromLocked</b> bit-field flag in the <b>Flags</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a> and <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_lock.md">D3DDDIARG_LOCK</a> structures (that is, both at creation and at lock time). When the hardware actively renders from a locked vertex buffer, the driver is not required to take any special action because the runtime will not overwrite any data in the locked vertex buffer . 

The runtime calls the user-mode display driver's <i>Lock</i> function to lock preallocated system memory surfaces as well. This operation allows the user-mode display driver to properly synchronize references to such surfaces that might be in the hardware command stream. The user-mode display driver can accomplish the synchronization by: 

<ul>
<li>
Flushing (that is, calling the runtime's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a> callback function) any outstanding commands as necessary.

</li>
<li>
Calling <b>pfnLockCb</b> with the appropriate allocation handle for commands that have already been submitted to hardware. 

</li>
</ul>
The user-mode display driver returns a pointer to the memory for the locked surface and the pitch of the surface in the <b>pSurfData</b> and <b>Pitch</b> members of the D3DDDIARG_LOCK structure. However, for preallocated system memory surfaces, the runtime ignores the driver-set memory and pitch, although the driver can still fail the <i>Lock</i> call (and thus fail back to the application). The runtime sets the <b>NotifyOnly</b> bit-field flag in the <b>Flags</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_lock.md">D3DDDIARG_LOCK</a> structure to differentiate <i>Lock</i> calls that lock preallocated system memory surfaces from other <i>Lock</i> calls. 




## -see-also

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationinfo.md">D3DDDI_ALLOCATIONINFO</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_lock.md">D3DDDIARG_LOCK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_LOCK callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

