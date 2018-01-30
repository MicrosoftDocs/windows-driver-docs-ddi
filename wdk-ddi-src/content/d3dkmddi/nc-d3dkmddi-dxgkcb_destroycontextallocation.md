---
UID: NC:d3dkmddi.DXGKCB_DESTROYCONTEXTALLOCATION
title: DXGKCB_DESTROYCONTEXTALLOCATION
author: windows-driver-content
description: Called by a WDDM 1.2 or later display miniport driver to free a resource that was previously allocated for a GPU or device-specific context.
old-location: display\dxgkcbdestroycontextallocation.htm
old-project: display
ms.assetid: f613e019-0b6d-43fc-a802-a6cd3803a00d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkcbdestroycontextallocation, DxgkCbDestroyContextAllocation callback function [Display Devices], DxgkCbDestroyContextAllocation, DXGKCB_DESTROYCONTEXTALLOCATION, DXGKCB_DESTROYCONTEXTALLOCATION, d3dkmddi/DxgkCbDestroyContextAllocation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3dkmddi.h
apiname:
-	DxgkCbDestroyContextAllocation
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKCB_DESTROYCONTEXTALLOCATION callback


## -description


Called by a WDDM 1.2 or later display miniport driver to free a resource that was previously allocated for a GPU or device-specific context.


## -prototype


````
DXGKCB_DESTROYCONTEXTALLOCATION DxgkCbDestroyContextAllocation;

NTSTATUS APIENTRY CALLBACK* DxgkCbDestroyContextAllocation(
  _In_ const HANDLE hAdapter,
  _In_ const HANDLE hAllocation
)
{ ... }
````


## -parameters




### -param hAdapter [in]

[in] A handle to the graphics adapter for which the allocation was created. The display miniport driver receives the handle from the <b>DeviceHandle</b> member of the <a href="..\dispmprt\ns-dispmprt-_dxgkrnl_interface.md">DXGKRNL_INTERFACE</a> structure in a call to its <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function.



### -param hAllocation [in]

[in] A handle that was assigned by the DirectX graphics subsystem to the allocation. The display miniport driver receives the handle from the <b>hAllocation</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_createcontextallocation.md">DXGKARGCB_CREATECONTEXTALLOCATION</a> structure in the call to the<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_createcontextallocation.md">DxgkCbCreateContextAllocation</a>
                                    function.


## -returns


<i>DxgkCbDestroyContextAllocation</i> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in Ntstatus.h.



## -remarks


The driver allocates  context resources by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_createcontextallocation.md">DxgkCbCreateContextAllocation</a>.

After the display miniport driver calls <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_createcontextallocation.md">DxgkCbCreateContextAllocation</a> to allocate a context resource, it can call <i>DxgkCbDestroyContextAllocation</i> to free the resource at any time.



## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_createcontextallocation.md">DxgkCbCreateContextAllocation</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_createcontextallocation.md">DXGKARGCB_CREATECONTEXTALLOCATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_DESTROYCONTEXTALLOCATION callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

