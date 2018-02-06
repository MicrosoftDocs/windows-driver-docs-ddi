---
UID: NC:d3dumddi.PFND3DDDI_SETDISPLAYMODE
title: PFND3DDDI_SETDISPLAYMODE
author: windows-driver-content
description: The SetDisplayMode function switches to a display mode or primary that is not supported by the GDI desktop.
old-location: display\setdisplaymode.htm
old-project: display
ms.assetid: d0e409fe-1c64-4468-b52e-b0ede39f6601
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.setdisplaymode, SetDisplayMode callback function [Display Devices], SetDisplayMode, PFND3DDDI_SETDISPLAYMODE, PFND3DDDI_SETDISPLAYMODE, d3dumddi/SetDisplayMode, UserModeDisplayDriver_Functions_939f1113-54d3-4e0e-b065-24226d9948c0.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	SetDisplayMode
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETDISPLAYMODE callback


## -description


The <i>SetDisplayMode</i> function switches to a display mode or primary that is not supported by the GDI desktop.


## -prototype


````
PFND3DDDI_SETDISPLAYMODE SetDisplayMode;

__checkReturn HRESULT APIENTRY SetDisplayMode(
  _In_       HANDLE                   hDevice,
  _In_ const D3DDDIARG_SETDISPLAYMODE *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *






#### - pData [in]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setdisplaymode.md">D3DDDIARG_SETDISPLAYMODE</a> structure that specifies parameters for setting the display mode.


## -returns


<i>SetDisplayMode</i> returns S_OK or an appropriate error result if the display mode is not successfully set.



## -remarks


The Microsoft Direct3D runtime calls <i>SetDisplayMode</i> to switch to a display mode or primary that is not supported by the GDI desktop. The following list describes examples of such primaries: 
<ul>
<li>
Primaries that are created with 10-bits-per-channel (10:10:10:2) display and render target formats (for example, D3DFMT_A2R10G10B10)

</li>
<li>
Multiple-sampled primaries where the multiple-sampling is performed while scanning-out 

</li>
<li>
Persistent primaries that are used by full-screen Microsoft DirectX version 9.L applications 

</li>
</ul>The Direct3D runtime calls the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a> function to create the primary to be scanned out. However, the driver should program the hardware to scan out only when its <i>SetDisplayMode</i> function is called. Therefore, the runtime sets the <b>hResource</b> and <b>SubResourceIndex</b> members of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setdisplaymode.md">D3DDDIARG_SETDISPLAYMODE</a> structure that is pointed to by the <i>pData</i> parameter to the primary that was created through the call to the driver's <i>CreateResource</i> function. The driver should then translate the primary that is represented by <b>hResource</b> and <b>SubResourceIndex</b> to a primary allocation handle. After the driver makes this translation, the driver should pass the resulting handle in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplaymodecb.md">pfnSetDisplayModeCb</a> function, which then initiates a call to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_commitvidpn.md">DxgkDdiCommitVidPn</a> function. 

The user-mode display driver can set the <b>hPrimaryAllocation</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_setdisplaymode.md">D3DDDICB_SETDISPLAYMODE</a> structure in the call to <b>pfnSetDisplayModeCb</b> to scan out any allocation. However, the allocation must be marked as a primary (that is, the user-mode display driver must have set the <b>Primary</b> bit-field flag in the <b>Flags</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationinfo.md">D3DDDI_ALLOCATIONINFO</a> structure in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a> function to create the allocation).



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setdisplaymode.md">D3DDDIARG_SETDISPLAYMODE</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplaymodecb.md">pfnSetDisplayModeCb</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETDISPLAYMODE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

