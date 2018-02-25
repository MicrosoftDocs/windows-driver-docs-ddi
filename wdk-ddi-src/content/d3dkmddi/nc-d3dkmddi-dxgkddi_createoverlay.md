---
UID: NC:d3dkmddi.DXGKDDI_CREATEOVERLAY
title: DXGKDDI_CREATEOVERLAY
author: windows-driver-content
description: The DxgkDdiCreateOverlay function enables the overlay hardware if the hardware is capable.
old-location: display\dxgkddicreateoverlay.htm
old-project: display
ms.assetid: 1ccdd16d-fd76-4039-b538-86c77b4e8cbb
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: DXGKDDI_CREATEOVERLAY, DmFunctions_61539b38-d12a-4642-926c-70c1cf1df34b.xml, DxgkDdiCreateOverlay, DxgkDdiCreateOverlay callback function [Display Devices], d3dkmddi/DxgkDdiCreateOverlay, display.dxgkddicreateoverlay
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
-	DxgkDdiCreateOverlay
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_CREATEOVERLAY callback


## -description


The <i>DxgkDdiCreateOverlay</i> function enables the overlay hardware if the hardware is capable.


## -prototype


````
DXGKDDI_CREATEOVERLAY DxgkDdiCreateOverlay;

NTSTATUS APIENTRY DxgkDdiCreateOverlay(
  _In_    const HANDLE                hAdapter,
  _Inout_       DXGKARG_CREATEOVERLAY *pCreateOverlay
)
{ ... }
````


## -parameters




### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pCreateOverlay [in, out]

[in/out] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createoverlay.md">DXGKARG_CREATEOVERLAY</a> structure that describes the overlay.


## -returns



<i>DxgkDdiCreateOverlay</i> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiCreateOverlay</i> successfully created the overlay.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters that were passed to <i>DxgkDdiCreateOverlay</i> contained errors that prevented it from completing.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiCreateOverlay</i> could not allocate memory that was required for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiCreateOverlay</i> could not complete because insufficient bandwidth was available or the requested overlay hardware could not complete the task.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_DRIVER_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver is not compatible with the user-mode display driver that initiated the call to <i>DxgkDdiCreateOverlay</i>. 

</td>
</tr>
</table>
 




## -remarks



<i>DxgkDdiCreateOverlay</i> should be made pageable.




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createoverlay.md">DXGKARG_CREATEOVERLAY</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_CREATEOVERLAY callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

