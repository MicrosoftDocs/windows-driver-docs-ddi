---
UID: NC:d3dkmddi.DXGKDDI_ESCAPE
title: DXGKDDI_ESCAPE
author: windows-driver-content
description: The DxgkDdiEscape function shares information with the user-mode display driver.
old-location: display\dxgkddiescape.htm
old-project: display
ms.assetid: 79a524cd-dec1-4ea8-a660-d9d9c644e162
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: DXGKDDI_ESCAPE, DmFunctions_41056daa-dfeb-4ba3-b453-b8d5dd94e8a3.xml, DxgkDdiEscape, DxgkDdiEscape callback function [Display Devices], d3dkmddi/DxgkDdiEscape, display.dxgkddiescape
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
-	DxgkDdiEscape
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_ESCAPE callback


## -description


The <i>DxgkDdiEscape</i> function shares information with the user-mode display driver.


## -prototype


````
DXGKDDI_ESCAPE DxgkDdiEscape;

NTSTATUS APIENTRY DxgkDdiEscape(
  _In_ const HANDLE         hAdapter,
  _In_ const DXGKARG_ESCAPE *pEscape
)
{ ... }
````


## -parameters




### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pEscape [in]

[in] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_escape.md">DXGKARG_ESCAPE</a> structure that contains information about the shared information.

<div class="alert"><b>Note</b>  In order for the <b>DxgkDdiEscape</b> call to be made under the second level, the <b>HardwareAccess</b> flag must be set within the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_escapeflags.md">D3DDDI_ESCAPEFLAGS</a> structure that is a member of <i>DXGKARG_ESCAPE</i>. If this flag is not set, then the call will fail.</div>
<div> </div>

## -returns



<i>DxgkDdiEscape</i> returns one of the following values:

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
<i>DxgkDdiEscape</i> successfully shared information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters that were passed to <i>DxgkDdiEscape</i> contained errors that prevented it from completing.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiEscape</i> could not allocate memory that was required for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PRIVILEGED_INSTRUCTION</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiEscape</i> detected nonprivileged instructions (that is, instructions that access memory beyond the privilege of the current central processing unit [CPU] process).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ILLEGAL_INSTRUCTION</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiEscape</i> detected instructions that graphics hardware could not support.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_DRIVER_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver is not compatible with the user-mode display driver that initiated the call to <i>DxgkDdiEscape</i>. 

</td>
</tr>
</table>
 




## -remarks



The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiEscape</i> function whenever the user-mode display driver must share information with the display miniport driver in a way that is not supported through other driver communications. 

<i>DxgkDdiEscape</i> should be made pageable.




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_escape.md">DXGKARG_ESCAPE</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_escapecb.md">pfnEscapeCb</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_ESCAPE callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

