---
UID: NC:d3dkmddi.DXGKDDI_COMMITVIDPN
title: DXGKDDI_COMMITVIDPN
author: windows-driver-content
description: The DxgkDdiCommitVidPn function makes a specified video present network (VidPN) active on a display adapter.
old-location: display\dxgkddicommitvidpn.htm
old-project: display
ms.assetid: 979b86e9-f3ff-4022-8c00-b6afc2b1f747
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
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
req.alt-api: DxgkDdiCommitVidPn
req.alt-loc: d3dkmddi.h
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
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_COMMITVIDPN callback



## -description
The <i>DxgkDdiCommitVidPn</i> function makes a specified video present network (VidPN) active on a display adapter.



## -prototype

````
DXGKDDI_COMMITVIDPN DxgkDdiCommitVidPn;

NTSTATUS APIENTRY DxgkDdiCommitVidPn(
  _In_ const HANDLE                    hAdapter,
  _In_ const DXGKARG_COMMITVIDPN CONST *pCommitVidPnArg
)
{ ... }
````


## -parameters

### -param hAdapter [in]

A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pCommitVidPnArg [in]

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_commitvidpn.md">DXGKARG_COMMITVIDPN</a> structure that contains function arguments.


## -returns
<i>DxgkDdiCommitVidPn</i> returns one of the values in the following list. The VidPN referred to in the list is the VidPN represented by <i>pCommitVidPnArg</i>-&gt;<b>hFunctionalVidPn</b>.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
<dd>
The driver successfully handled the function call.

</dd>
<dt><b>STATUS_GRAPHICS_GAMMA_RAMP_NOT_SUPPORTED</b></dt>
<dd>
The display adapter does not support all of the path gamma ramps in the VidPN.

</dd>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY</b></dt>
<dd>
The topology of the VidPN is invalid. In particular, <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_commitvidpn.md">DxgkDdiCommitVidPn</a> must return this value if <i>pCommitVidPnArg</i>-&gt;<b>MonitorConnectivityChecks</b> is equal to <b>D3DKMDT_MCC_ENFORCE</b> and one of the video outputs in the new VidPN's topology does not have a monitor connected.

</dd>
<dt><b>STATUS_GRAPHICS_PATH_CONTENT_GEOMETRY_TRANSFORMATION_NOT_SUPPORTED</b></dt>
<dd>
One of the present paths in the topology does not support the specified content transformation.

</dd>
<dt><b>STATUS_GRAPHICS_VIDPN_MODALITY_NOT_SUPPORTED</b></dt>
<dd>
The display adapter does not currently support the set of modes that are pinned in the VidPN.

</dd>
<dt><b>STATUS_NO_MEMORY</b></dt>
<dd>
The driver could not complete this request because of insufficient memory.

</dd>
</dl>The driver successfully handled the function call.

The display adapter does not support all of the path gamma ramps in the VidPN.

The topology of the VidPN is invalid. In particular, <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_commitvidpn.md">DxgkDdiCommitVidPn</a> must return this value if <i>pCommitVidPnArg</i>-&gt;<b>MonitorConnectivityChecks</b> is equal to <b>D3DKMDT_MCC_ENFORCE</b> and one of the video outputs in the new VidPN's topology does not have a monitor connected.

One of the present paths in the topology does not support the specified content transformation.

The display adapter does not currently support the set of modes that are pinned in the VidPN.

The driver could not complete this request because of insufficient memory.


## -remarks
For more information about how the display miniport driver should handle calls to <i>DxgkDdiCommitVidPn</i>, see <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_commitvidpn.md">DXGKARG_COMMITVIDPN</a>.

Beginning with Windows 8, if the display miniport driver sets the <b>SupportSmoothRotation</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a> structure, it must support updating the path rotation on the adapter using the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_updateactivevidpnpresentpath.md">DxgkDdiUpdateActiveVidPnPresentPath</a> function. The driver must always be able to set the path rotation during a call to the <i>DxgkDdiCommitVidPn</i> function.


## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_commitvidpn.md">DXGKARG_COMMITVIDPN</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_updateactivevidpnpresentpath.md">DxgkDdiUpdateActiveVidPnPresentPath</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_COMMITVIDPN callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

