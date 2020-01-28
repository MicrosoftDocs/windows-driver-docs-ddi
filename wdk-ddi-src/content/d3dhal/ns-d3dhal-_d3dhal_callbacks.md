---
UID: NS:d3dhal._D3DHAL_CALLBACKS
title: _D3DHAL_CALLBACKS (d3dhal.h)
description: D3DHAL_CALLBACKS is one of several callback structures that describe the Direct3D support provided by the driver.
old-location: display\d3dhal_callbacks.htm
tech.root: display
ms.assetid: 3b045732-a41f-47e7-9835-41e3ef54f14c
ms.date: 05/10/2018
ms.keywords: "*LPD3DHAL_CALLBACKS, D3DHAL_CALLBACKS, D3DHAL_CALLBACKS structure [Display Devices], LPD3DHAL_CALLBACKS, LPD3DHAL_CALLBACKS structure pointer [Display Devices], _D3DHAL_CALLBACKS, d3dhal/D3DHAL_CALLBACKS, d3dhal/LPD3DHAL_CALLBACKS, d3dstrct_2dc02d2c-6ae9-4f2e-9cb3-470926980537.xml, display.d3dhal_callbacks"
f1_keywords:
 - "d3dhal/D3DHAL_CALLBACKS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dhal.h
api_name:
- D3DHAL_CALLBACKS
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_CALLBACKS, *LPD3DHAL_CALLBACKS
---

# _D3DHAL_CALLBACKS structure


## -description


D3DHAL_CALLBACKS is one of several callback structures that describe the Direct3D support provided by the driver.


## -struct-fields




### -field dwSize

Specifies the size in bytes of this D3DHAL_CALLBACKS structure.


### -field ContextCreate

Points to the driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_contextcreatecb">D3dContextCreate</a> callback. A driver must implement the callback that this member points to.


### -field ContextDestroy

Points to the driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_contextdestroycb">D3dContextDestroy</a> callback. A driver must implement the callback that this member points to.


### -field ContextDestroyAll

Must be set to <b>NULL</b> in a Windows 2000 and later driver.


### -field SceneCapture

Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dSceneCapture</b> callback. For DirectX 7.0 and later, this callback was replaced by the handling of the D3DRENDERSTATE_SCENECAPTURE render state in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a> function.


### -field lpReserved10

Must be zero.


### -field lpReserved11

Must be zero.


### -field RenderState

Points to the driver-supplied D3DHAL_RENDERSTATEDATA callback. A driver must implement the callback that this member points to.


### -field RenderPrimitive

Points to the driver-supplied D3DHAL_RENDERPRIMITIVEDATA callback. A driver must implement the callback that this member points to.


### -field dwReserved

Specifies reserved fields and must be set to zero.


### -field TextureCreate

Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dTextureCreate</b> callback, or <b>NULL</b>. 


### -field TextureDestroy

Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dTextureDestroy</b> callback, or <b>NULL</b>.


### -field TextureSwap

Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dTextureSwap</b> callback, or <b>NULL</b>.


### -field TextureGetSurf

Must be set to <b>NULL</b> in a Windows 2000 and later driver. For DirectX 6.0, this was a pointer to the driver-supplied <b>D3dTextureGetSurf</b> callback, or <b>NULL</b>.


### -field lpReserved12

Must be zero.


### -field lpReserved13

Must be zero.


### -field lpReserved14

Must be zero.


### -field lpReserved15

Must be zero.


### -field lpReserved16

Must be zero.


### -field lpReserved17

Must be zero.


### -field lpReserved18

Must be zero.


### -field lpReserved19

Must be zero.


### -field lpReserved20

Must be zero.


### -field lpReserved21

Must be zero.


### -field GetState

Points to the driver-supplied D3DHAL_GETSTATEDATA callback. A driver must implement the callback that this member points to.


### -field dwReserved0

Must be zero.


### -field dwReserved1

Must be zero.


### -field dwReserved2

Must be zero.


### -field dwReserved3

Must be zero.


### -field dwReserved4

Must be zero.


### -field dwReserved5

Must be zero.


### -field dwReserved6

Must be zero.


### -field dwReserved7

Must be zero.


### -field dwReserved8

Must be zero


### -field dwReserved9

Must be zero.


## -remarks



The driver allocates this structure and sets appropriate values in all members. The driver's <a href="https://docs.microsoft.com/windows/desktop/api/winddi/nf-winddi-drvgetdirectdrawinfo">DrvGetDirectDrawInfo</a> function returns a pointer to this structure in the <b>lpD3DHALCallbacks</b> member of the <a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/ns-ddrawint-_dd_halinfo">DD_HALINFO</a> structure.

Texture management is now handled though opcodes that are managed in the driver's implementation of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_callbacks3">D3DHAL_CALLBACKS3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_contextcreatecb">D3dContextCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_contextdestroycb">D3dContextDestroy</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/nc-ddrawint-pdd_getdriverinfo">DdGetDriverInfo</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winddi/nf-winddi-drvgetdirectdrawinfo">DrvGetDirectDrawInfo</a>
 

 

