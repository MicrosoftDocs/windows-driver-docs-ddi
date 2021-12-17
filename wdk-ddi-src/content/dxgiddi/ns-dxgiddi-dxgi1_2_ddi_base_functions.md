---
UID: NS:dxgiddi.DXGI1_2_DDI_BASE_FUNCTIONS
title: DXGI1_2_DDI_BASE_FUNCTIONS (dxgiddi.h)
description: Contains pointers to functions that a Windows Display Driver Model (WDDM) 1.2 and later user-mode display driver can implement to perform low-level tasks like presenting rendered frames to an output, controlling gamma, getting notifications regarding shared and Windows Graphics Device Interface (GDI) interoperable surfaces, and managing a full-screen transition.
old-location: display\dxgi1_2_ddi_base_functions.htm
tech.root: display
ms.date: 12/09/2021
keywords: ["DXGI1_2_DDI_BASE_FUNCTIONS structure"]
ms.keywords: DXGI1_2_DDI_BASE_FUNCTIONS, DXGI1_2_DDI_BASE_FUNCTIONS structure [Display Devices], display.dxgi1_2_ddi_base_functions, dxgiddi/DXGI1_2_DDI_BASE_FUNCTIONS
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8,WDDM 1.2 and later
req.target-min-winversvr: Windows Server 2012
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
req.typenames: DXGI1_2_DDI_BASE_FUNCTIONS
f1_keywords:
 - DXGI1_2_DDI_BASE_FUNCTIONS
 - dxgiddi/DXGI1_2_DDI_BASE_FUNCTIONS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Dxgiddi.h
api_name:
 - DXGI1_2_DDI_BASE_FUNCTIONS
---

# DXGI1_2_DDI_BASE_FUNCTIONS structure

## -description

Contains pointers to functions that a Windows Display Driver Model (WDDM) 1.2 and later user-mode display driver can implement to perform low-level tasks like presenting rendered frames to an output, controlling gamma, getting notifications regarding shared and Windows Graphics Device Interface (GDI) interoperable surfaces, and managing a full-screen transition.

## -struct-fields

### -field pfnPresent

A pointer to the driver's [**PresentDXGI**](ns-dxgiddi-dxgi_ddi_base_functions.md) function.

### -field pfnGetGammaCaps

A pointer to the driver's [**GetGammaCapsDXGI**](ns-dxgiddi-dxgi_ddi_base_functions.md) function.

### -field pfnSetDisplayMode

A pointer to the driver's [**SetDisplayModeDXGI**](ns-dxgiddi-dxgi1_1_ddi_base_functions.md) function.

### -field pfnSetResourcePriority

A pointer to the driver's [**SetResourcePriorityDXGI**](ns-dxgiddi-dxgi_ddi_base_functions.md) function.

### -field pfnQueryResourceResidency

A pointer to the driver's [**QueryResourceResidencyDXGI**](ns-dxgiddi-dxgi_ddi_base_functions.md) function.

### -field pfnRotateResourceIdentities

A pointer to the driver's [**RotateResourceIdentitiesDXGI**](ns-dxgiddi-dxgi_ddi_base_functions.md) function.

### -field pfnBlt

A pointer to the driver's [**BltDXGI**](ns-dxgiddi-dxgi_ddi_base_functions.md) function.

The Direct3D runtime might set the **Flags** member of the [**DXGI_DDI_ARG_BLT**](ns-dxgiddi-dxgi_ddi_arg_blt.md) structure that the **pBltData** parameter points to in such a way as to require the [**Blt1DXGI**](ns-dxgiddi-dxgi1_2_ddi_base_functions) function to perform a [bit-block transfer (bitblt)](/windows-hardware/drivers/display/copying-bitmaps) operation that resolves multi-sampled resources, performs color-format conversion, and performs a stretch or shrink all at once. However, the Direct3D runtime will never set the **Flags** member of **DXGI_DDI_ARG_BLT1** to zero (that is, no flags set) together with the **DXGI_DDI_MODE_ROTATION_IDENTITY** value set in the **Rotate** member of **DXGI_DDI_ARG_BLT1** (that is, to indicate no rotation) to perform a straight memory copy operation. Instead, unless both resources are multi-sampled, the Direct3D runtime calls the driver's [**ResourceCopy**](../d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcecopy.md) or [**ResourceCopyRegion(D3D11_1)**](../d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_resourcecopyregion.md) function to perform a straight memory copy operation.

The quality of the stretch or shrink that the user-mode display driver performs must be as good as the stretch or shrink that a bilinear filter performs.

The Direct3D runtime will call the driver's [**Blt1DXGI**](ns-dxgiddi-dxgi1_2_ddi_base_functions.md) function infrequently. That is, the runtime should call **Blt1DXGI** no more than once or twice per frame because the runtime uses **Blt1DXGI** primarily to support a presentation.

 When the runtime calls [**Blt1DXGI**](ns-dxgiddi-dxgi1_2_ddi_base_functions.md) for a presentation, the runtime sets the **Present** bit-field flag in the **Flags** member of [**DXGI_DDI_ARG_BLT1**](ns-dxgiddi-dxgi_ddi_arg_blt1.md). The runtime sets the **Present** bit-field flag to inform the driver that there are extra requirements for the bitblt and that extra synchronization may be necessary (for example, the runtime might need to perform extra synchronization in computer configurations that contain two graphics adapters that each handle separate parts of the display). When the **Present** bit-field flag is set, the driver should perform a copy operation from an application's back buffers to the shared surface of the DWM. Because synchronization for this type of copy operation is inexact, tearing artifacts should be the worst type of artifacts that a user experiences. For this type of copy operation, the driver should not use a multi-pass approach by first resolving into the destination surface and then color converting the results in-place because the possible artifacts would be much worse.

If the driver supports returning **DXGI_DDI_ERR_UNSUPPORTED** during the creation of a primary surface (that is, returning **DXGI_DDI_ERR_UNSUPPORTED** from a call to its [**CreateResource(D3D10)**](../d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource.md) function with the **D3D10_DDI_BIND_PRESENT** flag set in the **BindFlags** member of [**D3D10DDIARG_CREATERESOURCE**](../d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource.md) along with the **pPrimaryDesc** member of **D3D10DDIARG_CREATERESOURCE** set to non-NULL), the driver must also support rotation during a copy operation. If the driver never returns **DXGI_DDI_ERR_UNSUPPORTED** from a call to its **CreateResource(D3D10)** or [**CreateResource(D3D11)**](../d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createresource.md) function, the runtime will never pass the **DXGI_DDI_MODE_ROTATION_ROTATE90**, **DXGI_DDI_MODE_ROTATION_ROTATE180**, or **DXGI_DDI_MODE_ROTATION_ROTATE270** value to the **Rotate** member of [**DXGI_DDI_ARG_BLT1**](ns-dxgiddi-dxgi_ddi_arg_blt1.md). Therefore, in this situation, the driver's [**Blt1DXGI**](ns-dxgiddi-dxgi1_2_ddi_base_functions.md) function is not required to support rotation.

The runtime sets a value in the **Rotate** member of [**DXGI_DDI_ARG_BLT1**](ns-dxgiddi-dxgi_ddi_arg_blt1.md) to indicate the number of degrees to rotate counter-clockwise the contents of the source before the driver copies the contents to the destination. Rotation is specified in increments of 90 degrees.

> [!NOTE]
>
> When the driver's [**Blt1DXGI**](ns-dxgiddi-dxgi1_2_ddi_base_functions.md) function copies sRGB-formatted content from a source surface to a non-sRGB destination surface, the driver should copy the sRGB content unchanged (that is, the driver should not perform the sRGB to linear conversion).

#### Source restrictions

The [**Blt1DXGI**](ns-dxgiddi-dxgi1_2_ddi_base_functions.md) function always uses a whole source subresource (versus some sub-rectangular area) to perform the bitblt operation. In addition, the source is a **D3D10DDIRESOURCE_TEXTURE2D** representation (specified in the **ResourceDimension** member of [**D3D10DDIARG_CREATERESOURCE**](../d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource.md) or [**D3D11DDIARG_CREATERESOURCE**](../d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource.md) when the source is created in a call to the user-mode display driver's [**CreateResource(D3D10)**](../d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource.md) or [**CreateResource(D3D11)**](../d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createresource.md) function, respectively). When the runtime sets the **Resolve** bitfield in the **Flags** member of [**DXGI_DDI_ARG_BLT1**](ns-dxgiddi-dxgi_ddi_arg_blt1.md), the source is a multi-sampled resource. The source resource is restricted to a resource in which the **D3D10_DDI_BIND_PRESENT** flag was set in the **BindFlags** member of **D3D10DDIARG_CREATERESOURCE** or **D3D11DDIARG_CREATERESOURCE**. The format of the source (specified in the **Format** member of **D3D10DDIARG_CREATERESOURCE** or **D3D11DDIARG_CREATERESOURCE**) is restricted to display mode formats, specified by the following values from the [**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format) enumeration:

* **DXGI_FORMAT_B5G6R5_UNORM**
* **DXGI_FORMAT_B5G5R5A1_UNORM**
* **DXGI_FORMAT_B8G8R8A8_UNORM** (See Note below.)
* **DXGI_FORMAT_B8G8R8X8_UNORM**
* **DXGI_FORMAT_R16G16B16A16_FLOAT**
* **DXGI_FORMAT_R10G10B10A2_UNORM**
* **DXGI_FORMAT_R8G8B8A8_UNORM**
* **DXGI_FORMAT_R8G8B8A8_UNORM_SRGB**

> [!NOTE]
>
> If the driver supports the source format **DXGI_FORMAT_B8G8R8A8_UNORM**, the following restrictions apply:
>
> * When the driver performs a bitblt operation from a floating-point format to an integer format such as BGRA8888, it must implicitly encode gamma into the results.
> * Conversely, when the driver performs a bitblt operation from an integer format to a floating-point format, it must implicitly remove gamma encoding from the results.

#### Destination restrictions

The destination is also a **D3D10DDIRESOURCE_TEXTURE2D** representation. The format of the destination is also restricted to display mode formats. The destination resource is restricted to a resource that is bound as a render target (**D3D10_DDI_BIND_RENDER_TARGET** set in the **BindFlags** member of [**D3D10DDIARG_CREATERESOURCE**](../d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource.md) or [**D3D11DDIARG_CREATERESOURCE**](../d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource.md)).

#### Creating a stereo back buffer

Beginning in Windows 8, if the driver must create a stereo back buffer, it should set members of the [**D3D10DDIARG_CREATERESOURCE**](../d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource.md) or [**D3D11DDIARG_CREATERESOURCE**](../d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createresource.md) structure, respectively, pointed to by the **pCreateResource** parameter of the [**CreateResource(D3D10)**](../d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource.md) or [**CreateResource(D3D11)**](../d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createresource.md) functions, as follows:

1. Set the **ArraySize** member to a value of 2.
2. Set the **D3D10_DDI_BIND_PRESENT** flag value in the **BindFlags** member.

Additionally, to support stereo presentation, the BltDXGI function must allow any values for the **DstSubresource** and **SrcSubresource** members of the [**DXGI_DDI_ARG_BLT**](ns-dxgiddi-dxgi_ddi_arg_blt.md) structure that are within the range of the source and destination resources.

### -field pfnResolveSharedResource

A pointer to the driver's [**ResolveSharedResourceDXGI**](ns-dxgiddi-dxgi1_1_ddi_base_functions.md) function.

### -field pfnBlt1

A pointer to the driver's  [**Blt1DXGI**](ns-dxgiddi-dxgi1_2_ddi_base_functions.md) function.

### -field pfnOfferResources

A pointer to the driver's [**pfnOfferResources**](../d3dumddi/nc-d3dumddi-pfnd3dddi_offerresources.md) function.

### -field pfnReclaimResources

Called by the DXGI runtime to reclaim video memory resources that the user-mode display driver  previously offered  for reuse. Implemented by WDDM 1.2 and later user-mode display drivers.

### -field pfnGetMultiplaneOverlayCaps

Called by the Microsoft DirectX Graphics Infrastructure (DXGI) runtime to request that the user-mode display driver get basic overlay plane capabilities. Optionally implemented by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers. The syntax of **pfnGetMultiplaneOverlayCaps** follows:

```cpp
pfnGetMultiPlaneOverlayCaps GetMultiPlaneOverlayCaps;

HRESULT __stdcall* GetMultiPlaneOverlayCaps(
    DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS *pCaps
)
{ ... }
```

The *pCaps* parameter is a pointer to a [DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS](ns-dxgiddi-_dxgi_ddi_arg_getmultiplaneoverlaycaps.md) structure that specifies the overlay plane capabilities.

**pfnGetMultiplaneOverlayCaps** returns one of the following values:

* S_OK: The driver successfully provided the overlay plane capabilities.
* D3DDDIERR_DEVICEREMOVED: The driver detected that the display adapter was removed, so the driver did not complete the operation. If the driver is not aware of the adapter removal, the driver is not required to return this error code.

### -field pfnGetMultiplaneOverlayFilterRange

This member is reserved and should be set to zero. Supported starting with Windows 8.1.

### -field pfnCheckMultiplaneOverlaySupport

Called by the Microsoft DirectX Graphics Infrastructure (DXGI) runtime to check the details on hardware support for multiplane overlays. The syntax of **pfnCheckMultiplaneOverlaySupport** is:

```cpp
PFND3DDDI_CHECKMULTIPLANEOVERLAYSUPPORT pfnCheckMultiplaneOverlaySupport;

HRESULT __stdcall* pfnCheckMultiplaneOverlaySupport(
   D3DDDIARG_CHECKMULTIPLANEOVERLAYSUPPORT *pSupport
)
{ ... }
```

The *pSupport* parameter is a pointer to a [**DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT**](../d3dkmddi/ns-d3dkmddi-_dxgkarg_checkmultiplaneoverlaysupport.md) structure that describes how to display to the destination surface.

If **pfnCheckMultiplaneOverlaySupport** succeeds, it returns S_OK. Otherwise, it returns an **HRESULT** error code.

### -field pfnPresentMultiplaneOverlay

A pointer to the driver's [**pfnPresentMultiplaneOverlay (DXGI)**](nc-dxgiddi-pfnddxgiddi_present_multiplane_overlaycb.md) function. Supported starting with Windows 8.1.

### -field pfnCheckMultiPlaneOverlaySupport

Called by the DXGI runtime to check the details on hardware support for multiplane overlays.

#### pSupport

A pointer to a [**DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT**](ns-dxgiddi-_dxgi_ddi_arg_checkmultiplaneoverlaysupport.md) structure that describes how to display to the destination surface.

## -see-also

[**CreateDevice(D3D10)**](../d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice.md)

[**D3D10DDIARG_CREATEDEVICE**](../d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createdevice.md)

[**DXGI1_3_DDI_BASE_FUNCTIONS**](ns-dxgiddi-dxgi1_3_ddi_base_functions.md)

[**DXGI_DDI_BASE_ARGS**](ns-dxgiddi-dxgi_ddi_base_args.md)

[**DXGI_DDI_BASE_FUNCTIONS**](ns-dxgiddi-dxgi_ddi_base_functions.md)
