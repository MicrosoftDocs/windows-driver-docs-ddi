---
UID: NS:dxgiddi.DXGI1_3_DDI_BASE_FUNCTIONS
title: DXGI1_3_DDI_BASE_FUNCTIONS
author: windows-driver-content
description: Contains pointers to functions that a Windows Display Driver Model (WDDM) 1.3 and later user-mode display driver can implement to perform low-level tasks like presenting rendered frames to an output, controlling gamma, getting notifications regarding shared and Windows Graphics Device Interface (GDI) interoperable surfaces, and managing a full-screen transition.
old-location: display\dxgi1_3_ddi_base_functions.htm
old-project: display
ms.assetid: F857BA54-A572-4376-83F3-573F90033261
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGI1_3_DDI_BASE_FUNCTIONS, DXGI1_3_DDI_BASE_FUNCTIONS structure [Display Devices], display.dxgi1_3_ddi_base_functions, dxgiddi/DXGI1_3_DDI_BASE_FUNCTIONS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Dxgiddi.h
api_name:
-	DXGI1_3_DDI_BASE_FUNCTIONS
product: Windows
targetos: Windows
req.typenames: DXGI1_3_DDI_BASE_FUNCTIONS
---

# DXGI1_3_DDI_BASE_FUNCTIONS structure


## -description


Contains pointers to functions that a Windows Display Driver Model (WDDM) 1.3 and later user-mode display driver can implement to perform low-level tasks like presenting rendered frames to an output, controlling gamma, getting notifications regarding shared and Windows Graphics Device Interface (GDI) interoperable surfaces, and managing a full-screen transition.


## -syntax


````
typedef struct DXGI1_3_DDI_BASE_FUNCTIONS {
  HRESULT (__stdcall *pfnPresent)(DXGI_DDI_ARG_PRESENT*);
  HRESULT (__stdcall *pfnGetGammaCaps)(DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS*);
  HRESULT (__stdcall *pfnSetDisplayMode)(DXGI_DDI_ARG_SETDISPLAYMODE*);
  HRESULT (__stdcall *pfnSetResourcePriority)(DXGI_DDI_ARG_SETRESOURCEPRIORITY*);
  HRESULT (__stdcall *pfnQueryResourceResidency)(DXGI_DDI_ARG_QUERYRESOURCERESIDENCY*);
  HRESULT (__stdcall *pfnRotateResourceIdentities)(DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES*);
  HRESULT (__stdcall *pfnBlt)(DXGI_DDI_ARG_BLT*);
  HRESULT (__stdcall *pfnResolveSharedResource)(DXGI_DDI_ARG_RESOLVESHAREDRESOURCE*);
  HRESULT (__stdcall *pfnBlt1)(DXGI_DDI_ARG_BLT1*);
  HRESULT (__stdcall *pfnOfferResources)(DXGI_DDI_ARG_OFFERRESOURCES*);
  HRESULT (__stdcall *pfnReclaimResources)(DXGI_DDI_ARG_RECLAIMRESOURCES*);
  HRESULT (__stdcall *pfnGetMultiPlaneOverlayCaps)(DXGI_DDI_ARG_GETMULTIPLANEOVERLAYCAPS*);
  HRESULT (__stdcall *pfnGetMultiplaneOverlayGroupCaps)(DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS *pGroupCaps);
  HRESULT (__stdcall *pfnReserved1)( void*);
  HRESULT (__stdcall *pfnPresentMultiPlaneOverlay)(DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY *pfnPresentMultiPlaneOverlay);
  HRESULT (__stdcall *pfnReserved2)(void*);
  HRESULT (__stdcall *pfnPresent1)(DXGI_DDI_ARG_PRESENT1 *pPresentData);
  HRESULT (__stdcall *pfnCheckPresentDurationSupport)(DXGI_DDI_ARG_CHECKPRESENTDURATIONSUPPORT*);
} DXGI1_3_DDI_BASE_FUNCTIONS;
````


## -struct-fields




### -field pfnPresent

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569179">PresentDXGI</a> function.


### -field pfnGetGammaCaps

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff566790">GetGammaCapsDXGI</a> function.


### -field pfnSetDisplayMode

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569536">SetDisplayModeDXGI</a> function.


### -field pfnSetResourcePriority

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569657">SetResourcePriorityDXGI</a> function.


### -field pfnQueryResourceResidency

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569224">QueryResourceResidencyDXGI</a> function.


### -field pfnRotateResourceIdentities

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569514">RotateResourceIdentitiesDXGI</a> function.


### -field pfnBlt

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff538252">BltDXGI</a> function.


### -field pfnResolveSharedResource

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569488">ResolveSharedResourceDXGI</a> function.


### -field pfnBlt1

A pointer to the driver's  <a href="https://msdn.microsoft.com/library/windows/hardware/hh406235">Blt1DXGI</a> function.


### -field pfnOfferResources

A pointer to the driver's <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_offerresources.md">pfnOfferResources</a> function.


### -field pfnReclaimResources

A pointer to the driver's <a href="https://msdn.microsoft.com/AF3DCD16-9F8C-442A-A9A5-9EA2BD1C3B84">pfnReclaimResources</a> function.


### -field pfnGetMultiplaneOverlayCaps

 


### -field pfnGetMultiplaneOverlayGroupCaps

Called by the DXGI runtime to request that the user-mode display driver  get a group of overlay plane capabilities. Optionally implemented by WDDM 1.3 and later user-mode display drivers. 

<div class="alert"><b>Note</b>  This function is called for each of the capability groups that the driver reports.</div>
<div> </div>


#### pGroupCaps

 A pointer to a <a href="..\dxgiddi\ns-dxgiddi-_dxgi_ddi_arg_getmultiplaneoverlaygroupcaps.md">DXGI_DDI_ARG_GETMULTIPLANEOVERLAYGROUPCAPS</a> structure that specifies the group of overlay plane capabilities.


### -field pfnReserved1

Reserved for system use.


### -field pfnPresentMultiplaneOverlay

 


### -field pfnReserved2

Reserved for system use.


### -field pfnPresent1

Notifies the user-mode display driver that an application finished rendering and that all ownership of the shared resource is released, and requests that the driver display to the destination surface.

The <b>hDevice</b> member of the <a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_arg_present1.md">DXGI_DDI_ARG_PRESENT1</a> structure that the <i>pPresentData</i> parameter points to is the same handle that the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function passed back to the runtime in the <b>hDrvDevice</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a> structure. Therefore, driver writers must define the type of this handle carefully. In addition, drivers can supply different implementations of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn469267">pfnPresent1(DXGI)</a> function based on which DDI implementation handled the call to <i>CreateDevice(D3D10)</i>. The runtime will never mix driver handles across DDI implementations.

The <b>pDXGIContext</b> member of <a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_arg_present1.md">DXGI_DDI_ARG_PRESENT1</a> is an opaque communication mechanism. The runtime passes this DXGI context to the driver. The driver should copy this DXGI context unchanged to the <b>pDXGIContext</b> member of the <a href="..\dxgiddi\ns-dxgiddi-dxgiddicb_present.md">DXGIDDICB_PRESENT</a> structure when the driver calls the <a href="..\dxgiddi\nc-dxgiddi-pfnddxgiddi_presentcb.md">pfnPresentCbDXGI</a> function.

The driver must submit all partially built render data (command buffers) using the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a> function, and the driver must make a single call to <a href="..\dxgiddi\nc-dxgiddi-pfnddxgiddi_presentcb.md">pfnPresentCbDXGI</a>. When calling either of these callbacks, the driver must follow the threading rules of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569179">PresentDXGI</a> function.

<div class="alert"><b>Note</b>    When the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/dn469267">pfnPresent1(DXGI)</a> function copies sRGB-formatted content from a source surface to a non-sRGB destination surface, the driver should copy the sRGB content unchanged (that is, the driver should not perform the sRGB to linear conversion).</div>
<div> </div>
Threading rules

These rules apply whether the driver supports free threading or not:<ul>
<li>The driver indicates support for free threading by setting the <b>Caps</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a> structure to <b>D3D11DDICAPS_FREETHREADED</b>. In this case:<ul>
<li>Only a single thread can be working against an HCONTEXT context handle at a time.</li>
<li>The driver must call <a href="..\dxgiddi\nc-dxgiddi-pfnddxgiddi_presentcb.md">pfnPresentCbDXGI</a> only when the driver’s <a href="https://msdn.microsoft.com/library/windows/hardware/dn469267">pfnPresent1(DXGI)</a> function is called, and by the same thread that called <i>pfnPresent1(DXGI)</i>.</li>
</ul>
</li>
<li>When the driver doesn’t indicate support for free-threading, it can only call the callback functions when a thread has called into the driver. The driver also must still call the <a href="..\dxgiddi\nc-dxgiddi-pfnddxgiddi_presentcb.md">pfnPresentCbDXGI</a> callback within the context of <a href="https://msdn.microsoft.com/library/windows/hardware/dn469267">pfnPresent1(DXGI)</a>.</li>
</ul>For further info on threading, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.



#### pPresentData

[in] A pointer to a <a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_arg_present1.md">DXGI_DDI_ARG_PRESENT1</a> structure that describes how to display to the destination surface. 


### -field pfnCheckPresentDurationSupport

A pointer to the driver's <a href="..\dxgiddi\ns-dxgiddi-_dxgi_ddi_arg_checkpresentdurationsupport.md">pfnCheckPresentDurationSupport(DXGI)</a> function.


#### - pfnGetMultiPlaneOverlayCaps

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/dn265493">pfnGetMultiPlaneOverlayCaps</a> function.


#### - pfnPresentMultiPlaneOverlay

A pointer to the driver's <a href="..\dxgiddi\nc-dxgiddi-pfnddxgiddi_present_multiplane_overlaycb.md">pfnPresentMultiplaneOverlay (DXGI)</a> function.


## -remarks



For more info on how to use this structure, see <a href="https://msdn.microsoft.com/3a49d7cb-984f-4e4f-a549-5c0442e1c45a">Supporting the DXGI DDI</a>.




## -see-also

<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_base_args.md">DXGI_DDI_BASE_ARGS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a>



<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_base_functions.md">DXGI_DDI_BASE_FUNCTIONS</a>



<a href="..\dxgiddi\ns-dxgiddi-dxgi1_2_ddi_base_functions.md">DXGI1_2_DDI_BASE_FUNCTIONS</a>



 

 


