---
UID: NC:d3dkmddi.DXGKDDI_ISSUPPORTEDVIDPN
title: DXGKDDI_ISSUPPORTEDVIDPN
author: windows-driver-content
description: The DxgkDdiIsSupportedVidPn function determines whether a specified VidPN is supported on a display adapter.
old-location: display\dxgkddiissupportedvidpn.htm
old-project: display
ms.assetid: 96e96366-6306-4d20-8752-e942f2ed4069
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.dxgkddiissupportedvidpn, DxgkDdiIsSupportedVidPn callback function [Display Devices], DxgkDdiIsSupportedVidPn, DXGKDDI_ISSUPPORTEDVIDPN, DXGKDDI_ISSUPPORTEDVIDPN, d3dkmddi/DxgkDdiIsSupportedVidPn, DmFunctions_222f2c38-00c6-466f-b653-3c9529f93849.xml
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
-	DxgkDdiIsSupportedVidPn
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_ISSUPPORTEDVIDPN callback


## -description


The <i>DxgkDdiIsSupportedVidPn</i> function determines whether a specified VidPN is supported on a display adapter.


## -prototype


````
DXGKDDI_ISSUPPORTEDVIDPN DxgkDdiIsSupportedVidPn;

NTSTATUS APIENTRY DxgkDdiIsSupportedVidPn(
  _In_    const HANDLE                   hAdapter,
  _Inout_       DXGKARG_ISSUPPORTEDVIDPN *pIsSupportedVidPnArg
)
{ ... }
````


## -parameters




### -param hAdapter [in]

A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pIsSupportedVidPn








#### - pIsSupportedVidPnArg [in, out]

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_issupportedvidpn.md">DXGKARG_ISSUPPORTEDVIDPN</a> structure. On input, the caller supplies the <b>hDesiredVidPn</b> member of the structure. On return, the <b>IsVidPnSupported</b> member receives a Boolean value that indicates whether the VidPN is supported (<b>TRUE</b>) or not supported (<b>FALSE</b>).


## -returns



<i>DxgkDdiIsSupportedVidPn</i> returns one of the following values

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
The topology of the VidPN is valid. The <b>IsVidPnSupported</b> structure member is set to either <b>TRUE</b> or <b>FALSE</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY</b></dt>
</dl>
</td>
<td width="60%">
The topology of the VidPN implementation is invalid. The <b>IsVidPnSupported</b> structure member is set to <b>FALSE</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
The function failed because it was unable to allocate memory.

</td>
</tr>
</table>
 




## -remarks



For more information about the analysis that this function must perform, see <a href="https://msdn.microsoft.com/ebf001fb-e445-4534-8e89-60e1b06b2d6e">Determining Whether a VidPN is Supported on a Display Adapter</a><u>.</u>

If pIsSupportedVidPnArg-&gt;hDesiredVidPn is zero, <i>DxgkDdiIsSupportedVidPn</i> must set pIsSupportedVidPnArg-&gt;IsVidPnSupported to <b>TRUE</b>, the idea being that the display adapter can always be configured to display nothing.

<i>DxgkDdiIsSupportedVidPn</i> should be made pageable.




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_ISSUPPORTEDVIDPN callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

