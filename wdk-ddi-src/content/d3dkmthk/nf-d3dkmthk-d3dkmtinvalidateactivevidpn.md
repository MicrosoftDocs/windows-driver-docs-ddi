---
UID: NF:d3dkmthk.D3DKMTInvalidateActiveVidPn
title: D3DKMTInvalidateActiveVidPn function (d3dkmthk.h)
description: The D3DKMTInvalidateActiveVidPn function invalidates the active video present network (VidPN) currently in use. Note   This function is obsolete in Windows 7 and later versions of the Windows operating systems.
old-location: display\d3dkmtinvalidateactivevidpn.htm
ms.date: 02/28/2022
keywords: ["D3DKMTInvalidateActiveVidPn function"]
ms.keywords: D3DKMTInvalidateActiveVidPn, D3DKMTInvalidateActiveVidPn function [Display Devices], OpenGL_Functions_3c74c218-cf17-4a86-af8e-da565b3cffd4.xml, d3dkmthk/D3DKMTInvalidateActiveVidPn, display.d3dkmtinvalidateactivevidpn
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTInvalidateActiveVidPn
 - d3dkmthk/D3DKMTInvalidateActiveVidPn
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
---

# D3DKMTInvalidateActiveVidPn function

## -description

The **D3DKMTInvalidateActiveVidPn** function invalidates the active video present network (VidPN) currently in use.

> [!NOTE]
> This function is obsolete in Windows 7 and later versions of Windows operating systems.

## -parameters

### -param unnamedParam1 [in]

A pointer to a [D3DKMT_INVALIDATEACTIVEVIDPN](ns-d3dkmthk-_d3dkmt_invalidateactivevidpn.md) structure that describes parameters that invalidate the active VidPN currently in use.

## -returns

**D3DKMTInvalidateActiveVidPn** returns one of the following values:

| Return code | Description |
|--|--|
| STATUS_SUCCESS | The VidPN currently in use was successfully invalidated. |
| STATUS_GRAPHICS_INVALID_DISPLAY_ADAPTER | No graphics adapter was specified in the hAdapter member of [D3DKMT_INVALIDATEACTIVEVIDPN](ns-d3dkmthk-_d3dkmt_invalidateactivevidpn.md)  to invalidate the VidPN for. |
| STATUS_NO_MEMORY | **D3DKMTInvalidateActiveVidPn** could not complete because of insufficient memory. |
| STATUS_NOT_SUPPORTED | The display mode that is requested by the OpenGL installable client driver (ICD) in the buffer pointed to by the pPrivateDriverData member of [D3DKMT_INVALIDATEACTIVEVIDPN](ns-d3dkmthk-_d3dkmt_invalidateactivevidpn.md)  is not supported by the display miniport driver. This status value will also be returned if this function is called on a computer running Windows 7 and later by a display miniport driver with DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN7. |
| STATUS_DEVICE_REMOVED | The graphics adapter was stopped. |
| STATUS_GRAPHICS_NO_RECOMMENDED_FUNCTIONAL_VIDPN | The display miniport driver did not recommend a VidPN to replace the VidPN currently in use. |

This function might also return other **NTSTATUS** values.

## -remarks

When the **D3DKMTInvalidateActiveVidPn** function is called to invalidate the VidPN currently in use, the current VidPN is replaced with a new VidPN that the display miniport driver recommends. Because the display miniport driver must recommend a new VidPN, the display miniport driver must be able to determine the display mode that the OpenGL ICD requires from the buffer pointed to by the **pPrivateDriverData** member of [D3DKMT_INVALIDATEACTIVEVIDPN](ns-d3dkmthk-_d3dkmt_invalidateactivevidpn.md).

The OpenGL ICD can call **D3DKMTInvalidateActiveVidPn** for display modes (for example, clone-view mode) that are not supported by using the more general call to the [D3DKMTSetDisplayMode](nf-d3dkmthk-d3dkmtsetdisplaymode.md) function.

## -see-also

[D3DKMTSetDisplayMode](nf-d3dkmthk-d3dkmtsetdisplaymode.md)

[D3DKMT_INVALIDATEACTIVEVIDPN](ns-d3dkmthk-_d3dkmt_invalidateactivevidpn.md)
