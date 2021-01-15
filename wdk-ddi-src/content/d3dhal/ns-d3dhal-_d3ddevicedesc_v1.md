---
UID: NS:d3dhal._D3DDeviceDesc_V1
title: _D3DDeviceDesc_V1 (d3dhal.h)
description: Obsolete in DirectX 8.0 and later versions; see Remarks. The D3DDEVICEDESC_V1 structure describes the 3D capabilities of a device.
old-location: display\d3ddevicedesc_v1.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDeviceDesc_V1 structure"]
ms.keywords: "*LPD3DDEVICEDESC_V1, D3DDEVICEDESC_V1, D3DDEVICEDESC_V1 structure [Display Devices], LPD3DDEVICEDESC_V1, LPD3DDEVICEDESC_V1 structure pointer [Display Devices], _D3DDeviceDesc_V1, d3dhal/D3DDEVICEDESC_V1, d3dhal/LPD3DDEVICEDESC_V1, d3dstrct_111d5153-fb7f-4c2b-acc5-65818723e263.xml, display.d3ddevicedesc_v1"
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
targetos: Windows
req.typenames: D3DDEVICEDESC_V1, *LPD3DDEVICEDESC_V1
f1_keywords:
 - _D3DDeviceDesc_V1
 - d3dhal/_D3DDeviceDesc_V1
 - LPD3DDEVICEDESC_V1
 - d3dhal/LPD3DDEVICEDESC_V1
 - D3DDEVICEDESC_V1
 - d3dhal/D3DDEVICEDESC_V1
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dhal.h
api_name:
 - _D3DDeviceDesc_V1
 - LPD3DDEVICEDESC_V1
 - D3DDEVICEDESC_V1
---

# _D3DDeviceDesc_V1 structure


## -description

   Obsolete in DirectX 8.0 and later versions; see Remarks.
   

The D3DDEVICEDESC_V1 structure describes the 3D capabilities of a device.

## -struct-fields

### -field dwSize

Specifies the size in bytes of this D3DDEVICEDESC_V1 structure.

### -field dwFlags

Identifies the members of this structure that contain valid data. This member can be a bitwise OR of any of the following values:

| **Value** | **Meaning** | 
|:--|:--|
| D3DDD_BCLIPPING | The bClipping member contains valid data. | 
| D3DDD_COLORMODEL | The dcmColorModel member contains valid data. | 
| D3DDD_DEVCAPS | The dwDevCaps member contains valid data. | 
| D3DDD_DEVICERENDERBITDEPTH | The dwDeviceRenderBitDepthmember contains valid data. | 
| D3DDD_DEVICEZBUFFERBITDEPTH | The dwDeviceZBufferBitDepthmember contains valid data. | 
| D3DDD_LIGHTINGCAPS | The dlcLightingCaps member contains valid data. | 
| D3DDD_LINECAPS | The dpcLineCaps member contains valid data. | 
| D3DDD_MAXBUFFERSIZE | The dwMaxBufferSize member contains valid data. | 
| D3DDD_MAXVERTEXCOUNT | The dwMaxVertexCount member contains valid data. | 
| D3DDD_TRANSFORMCAPS | The dtcTransformCaps member contains valid data. | 
| D3DDD_TRICAPS | The dpcTriCaps member contains valid data. |

### -field dcmColorModel

Specifies the device's color model.

### -field dwDevCaps

Identifies the capabilities of the device. This member can be a bitwise OR of any of the following values:

| **Value** | **Meaning** | 
|:--|:--|
| D3DDEVCAPS_CANBLTSYSTONONLOCAL | The device supports a TexBlt from system memory to sublocal video memory. | 
| D3DDEVCAPS_CANRENDERAFTERFLIP | The device can queue rendering commands after a page flip. Devices must support this capability on Windows 2000 and later, meaning that the driver would always set this flag. | 
| D3DDEVCAPS_DRAWPRIMITIVES2 | The device can support [D3dDrawPrimitives2](./nc-d3dhal-lpd3dhal_drawprimitives2cb.md) . | 
| D3DDEVCAPS_DRAWPRIMITIVES2EX | The device can support Extended [D3dDrawPrimitives2](./nc-d3dhal-lpd3dhal_drawprimitives2cb.md) ; i.e. a DX7-compliant driver. | 
| D3DDEVCAPS_DRAWPRIMTLVERTEX | The device can draw TLVERTEX primitives. This flag is obsolete but must be set by the driver. | 
| D3DDEVCAPS_EXECUTESYSTEMMEMORY | The device can use execute buffers from system memory. The driver must always set this bit. | 
| D3DDEVCAPS_EXECUTEVIDEOMEMORY | The device can use execute buffers from display memory. The driver must never set this bit. | 
| D3DDEVCAPS_FLOATTLVERTEX | The device accepts floating-point for posttransform vertex data. This flag is obsolete but must be set by the driver. | 
| D3DDEVCAPS_HWRASTERIZATION | The device has hardware acceleration for rasterization. | 
| D3DDEVCAPS_HWTRANSFORMANDLIGHT | The device can support transformation and lighting in hardware. D3DDEVCAPS_DRAWPRIMITIVES2EX must also be set. | 
| D3DDEVCAPS_SEPARATETEXTUREMEMORIES | The device is texturing from separate memory pools. Setting this capability bit indicates to DirectX 8.0 and later versions of applications that they are disabled from simultaneously using multiple textures. | 
| D3DDEVCAPS_SORTDECREASINGZ | The device needs data sorted for decreasing depth. | 
| D3DDEVCAPS_SORTEXACT | The device needs data sorted exactly. | 
| D3DDEVCAPS_SORTINCREASINGZ | The device needs data sorted for increasing depth. | 
| D3DDEVCAPS_TEXTURENONLOCALVIDEOMEMORY | The device can texture from nonlocal video memory. | 
| D3DDEVCAPS_TLVERTEXSYSTEMMEMORY | The device can use buffers from system memory for transformed and lit vertices. This flag is obsolete but must be set by the driver. | 
| D3DDEVCAPS_TLVERTEXVIDEOMEMORY | The device can use buffers from display memory for transformed and lit vertices. This flag is obsolete and must not be set by the driver. | 
| D3DDEVCAPS_TEXTURESYSTEMMEMORY | The device can retrieve textures from system memory. | 
| D3DDEVCAPS_TEXTUREVIDEOMEMORY | The device can retrieve textures from device memory. |

### -field dtcTransformCaps

Specifies a D3DTRANSFORMCAPS structure that specifies the transformation capabilities of the device. The driver must set the <b>dwCaps</b> member of that structure to zero.

### -field bClipping

Set to <b>TRUE</b> by the driver if the device can perform 3D clipping.

### -field dlcLightingCaps

Specifies the lighting capabilities of the device. This is a <a href="/windows-hardware/drivers/ddi/d3dcaps/ns-d3dcaps-_d3dlightingcaps">D3DLIGHTINGCAPS</a> structure. The driver must set the <b>dwCaps</b>, <b>dwLightingModel</b>, and <b>dwNumLights</b> members of that structure to zero.

### -field dpcLineCaps

Specifies a <a href="/windows-hardware/drivers/ddi/d3dcaps/ns-d3dcaps-_d3dprimcaps">D3DPRIMCAPS</a> structure that defines the drawing capabilities of the device for line primitives.

### -field dpcTriCaps

Specifies a <a href="/windows-hardware/drivers/ddi/d3dcaps/ns-d3dcaps-_d3dprimcaps">D3DPRIMCAPS</a> structure that defines the drawing capabilities of the device for triangle primitives.

### -field dwDeviceRenderBitDepth

Specifies the device's rendering bit-depth. This member can be a bitwise OR of the following DirectDraw bit-depth constants: DDBD_8, DDBD_16, DDBD_24, or DDBD_32.

### -field dwDeviceZBufferBitDepth

Specifies the device's z-buffer bit-depth. This member can be a bitwise OR of the following DirectDraw bit-depth constants: DDBD_8, DDBD_16, DDBD_24, or DDBD_32.

### -field dwMaxBufferSize

Must be set to zero.

### -field dwMaxVertexCount

DirectX 7 and later versions

DirectX 6

## -remarks

This structure has been replaced by D3DCAPS8 (see the DirectX 8.0 SDK documentation) for DirectX 8.0 and later runtimes, but is required for legacy runtime (DirectX 7.0 and earlier) compatibility. See <a href="/windows-hardware/drivers/display/reporting-directx-8-0-style-direct3d-capabilities">Reporting DirectX 8.0 Style Direct3D Capabilities</a> for details.

The driver's <a href="/windows/win32/api/winddi/nf-winddi-drvgetdirectdrawinfo">DrvGetDirectDrawInfo</a> function returns this information in the <a href="/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_globaldriverdata">D3DHAL_GLOBALDRIVERDATA</a> structure that the <b>lpD3DGlobalDriverData</b> member of the <a href="/windows/win32/api/ddrawint/ns-ddrawint-dd_halinfo">DD_HALINFO</a> structure points to.

The Direct3D runtime constructs the application-level D3DDEVICEDESC7 structure (documented in the Microsoft Windows SDK documentation) from the information returned in the D3DDEVICEDESC_V1 structure and the extended capabilities queried through the driver's <a href="/windows/win32/api/ddrawint/nc-ddrawint-pdd_getdriverinfo">DdGetDriverInfo</a> function. While some of the <b>dwDevCaps</b> flags are obsolete at the driver level, the driver must set them appropriately in order for applications to work correctly.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_globaldriverdata">D3DHAL_GLOBALDRIVERDATA</a>



<a href="/windows-hardware/drivers/ddi/d3dcaps/ns-d3dcaps-_d3dlightingcaps">D3DLIGHTINGCAPS</a>



<a href="/windows-hardware/drivers/ddi/d3dcaps/ns-d3dcaps-_d3dprimcaps">D3DPRIMCAPS</a>



<a href="/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>



<a href="/windows/win32/api/ddrawint/ns-ddrawint-dd_halinfo">DD_HALINFO</a>



<a href="/windows/win32/api/ddrawint/nc-ddrawint-pdd_getdriverinfo">DdGetDriverInfo</a>



<a href="/windows/win32/api/winddi/nf-winddi-drvgetdirectdrawinfo">DrvGetDirectDrawInfo</a>

