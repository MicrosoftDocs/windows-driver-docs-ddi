---
UID: NF:d3dkmthk.D3DKMTInvalidateActiveVidPn
title: D3DKMTInvalidateActiveVidPn function (d3dkmthk.h)
description: The D3DKMTInvalidateActiveVidPn function invalidates the active video present network (VidPN) currently in use. Note   This function is obsolete in Windows 7 and later versions of the Windows operating systems.
old-location: display\d3dkmtinvalidateactivevidpn.htm
ms.assetid: a7cac46d-b64d-4362-99ab-179aa6525ba2
ms.date: 05/10/2018
keywords: ["D3DKMTInvalidateActiveVidPn function"]
ms.keywords: D3DKMTInvalidateActiveVidPn, D3DKMTInvalidateActiveVidPn function [Display Devices], OpenGL_Functions_3c74c218-cf17-4a86-af8e-da565b3cffd4.xml, d3dkmthk/D3DKMTInvalidateActiveVidPn, display.d3dkmtinvalidateactivevidpn
f1_keywords:
 - "d3dkmthk/D3DKMTInvalidateActiveVidPn"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems for display miniport drivers with version < DXGKDDI_INTERFACE_VERSION_WIN7.
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Gdi32.dll
- API-MS-Win-dx-d3dkmt-l1-1-0.dll
- API-MS-Win-dx-d3dkmt-l1-1-1.dll
- API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
- D3DKMTInvalidateActiveVidPn
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTInvalidateActiveVidPn function

## -description

The <b>D3DKMTInvalidateActiveVidPn</b> function invalidates the active video present network (VidPN) currently in use.

<div class="alert"><b>Note</b>    This function is obsolete in Windows 7 and later versions of the Windows operating systems.</div>
<div> </div>

## -parameters

### -param D3DKMT_INVALIDATEACTIVEVIDPN

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_invalidateactivevidpn">D3DKMT_INVALIDATEACTIVEVIDPN</a> structure that describes parameters that invalidate the active VidPN currently in use.

## -returns

<b>D3DKMTInvalidateActiveVidPn</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The VidPN currently in use was successfully invalidated. | 
| **STATUS_GRAPHICS_INVALID_DISPLAY_ADAPTER** | No graphics adapter was specified in the hAdapter member of [D3DKMT_INVALIDATEACTIVEVIDPN](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_invalidateactivevidpn)  to invalidate the VidPN for. | 
| **STATUS_NO_MEMORY** | [D3DKMTInvalidateActiveVidPn](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtinvalidateactivevidpn)  could not complete because of insufficient memory. | 
| **STATUS_NOT_SUPPORTED** | The display mode that is requested by the OpenGL installable client driver (ICD) in the buffer pointed to by the pPrivateDriverData member of [D3DKMT_INVALIDATEACTIVEVIDPN](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_invalidateactivevidpn)  is not supported by the display miniport driver. This status value will also be returned if this function is called on a computer running Windows 7 and later by a display miniport driver with DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN7. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped. | 
| **STATUS_GRAPHICS_NO_RECOMMENDED_FUNCTIONAL_VIDPN** | The display miniport driver did not recommend a VidPN to replace the VidPN currently in use. | 

This function might also return other NTSTATUS values.

## -remarks

When the <b>D3DKMTInvalidateActiveVidPn</b> function is called to invalidate the VidPN currently in use, the current VidPN is replaced with a new VidPN that the display miniport driver recommends. Because the display miniport driver must recommend a new VidPN, the display miniport driver must be able to determine the display mode that the OpenGL ICD requires from the buffer pointed to by the <b>pPrivateDriverData</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_invalidateactivevidpn">D3DKMT_INVALIDATEACTIVEVIDPN</a>.

The OpenGL ICD can call <b>D3DKMTInvalidateActiveVidPn</b> for display modes (for example, clone-view mode) that are not supported by using the more general call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsetdisplaymode">D3DKMTSetDisplayMode</a> function. 

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsetdisplaymode">D3DKMTSetDisplayMode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_invalidateactivevidpn">D3DKMT_INVALIDATEACTIVEVIDPN</a>
 

 

