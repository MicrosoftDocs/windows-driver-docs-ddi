---
UID: NC:d3dkmddi.DXGKDDI_DESCRIBEALLOCATION
title: DXGKDDI_DESCRIBEALLOCATION
author: windows-driver-content
description: The DxgkDdiDescribeAllocation function retrieves information about an existing allocation that is not otherwise available to the Microsoft DirectX graphics kernel subsystem.
old-location: display\dxgkddidescribeallocation.htm
old-project: display
ms.assetid: 8ee65716-496c-4b0f-baa7-34a625847d5f
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: DXGKDDI_DESCRIBEALLOCATION, DmFunctions_ba74cf3f-f0be-401c-8232-0672d490221a.xml, DxgkDdiDescribeAllocation, DxgkDdiDescribeAllocation callback function [Display Devices], d3dkmddi/DxgkDdiDescribeAllocation, display.dxgkddidescribeallocation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DxgkDdiDescribeAllocation
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_DESCRIBEALLOCATION callback


## -description


The <i>DxgkDdiDescribeAllocation</i> function retrieves information about an existing allocation that is not otherwise available to the Microsoft DirectX graphics kernel subsystem.


## -prototype


````
DXGKDDI_DESCRIBEALLOCATION DxgkDdiDescribeAllocation;

NTSTATUS APIENTRY DxgkDdiDescribeAllocation(
  _In_    const HANDLE                     hAdapter,
  _Inout_       DXGKARG_DESCRIBEALLOCATION *pDescribeAllocation
)
{ ... }
````


## -parameters




### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pDescribeAllocation [in, out]

[in/out] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_describeallocation.md">DXGKARG_DESCRIBEALLOCATION</a> structure that describes an existing allocation.


## -returns



<i>DxgkDdiDescribeAllocation</i> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



Because the DirectX graphics kernel subsystem does not necessarily maintain records of allocations, the graphics kernel subsystem calls <i>DxgkDdiDescribeAllocation</i> to request that the display miniport driver return information about existing allocations. Currently, the display miniport driver must be able to return this information for the following allocations:

<ul>
<li>
Allocations that are also primaries (that is, allocations that the user-mode display driver created by setting the <b>Primary</b> bit-field flag in the <b>Flags</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationinfo.md">D3DDDI_ALLOCATIONINFO</a> structure in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a> function).

</li>
<li>
Allocations that might be the source of a presentation (that is, allocations that are represented by the <b>hSource</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_present.md">DXGKARG_PRESENT</a> structure in a call to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a> function).

</li>
</ul>
<i>DxgkDdiDescribeAllocation</i> should be made pageable.




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationinfo.md">D3DDDI_ALLOCATIONINFO</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_describeallocation.md">DXGKARG_DESCRIBEALLOCATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_DESCRIBEALLOCATION callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

