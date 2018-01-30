---
UID: NS:dxgiddi.DXGI1_2_DDI_BASE_FUNCTIONS
title: DXGI1_2_DDI_BASE_FUNCTIONS
author: windows-driver-content
description: Contains pointers to functions that a Windows Display Driver Model (WDDM) 1.2 and later user-mode display driver can implement to perform low-level tasks like presenting rendered frames to an output, controlling gamma, getting notifications regarding shared and Windows Graphics Device Interface (GDI) interoperable surfaces, and managing a full-screen transition.
old-location: display\dxgi1_2_ddi_base_functions.htm
old-project: display
ms.assetid: 7A1CD16A-4B7A-40FE-8650-AAD8CAC10FB0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: dxgiddi/DXGI1_2_DDI_BASE_FUNCTIONS, DXGI1_2_DDI_BASE_FUNCTIONS structure [Display Devices], DXGI1_2_DDI_BASE_FUNCTIONS, display.dxgi1_2_ddi_base_functions
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Dxgiddi.h
apiname:
-	DXGI1_2_DDI_BASE_FUNCTIONS
product: Windows
targetos: Windows
req.typenames: DXGI1_2_DDI_BASE_FUNCTIONS
---

# DXGI1_2_DDI_BASE_FUNCTIONS structure


## -description


Contains pointers to functions that a Windows Display Driver Model (WDDM) 1.2 and later user-mode display driver can implement to perform low-level tasks like presenting rendered frames to an output, controlling gamma, getting notifications regarding shared and Windows Graphics Device Interface (GDI) interoperable surfaces, and managing a full-screen transition.


## -syntax


````
typedef struct _DXGI1_2_DDI_BASE_FUNCTIONS {
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
  HRESULT (__stdcall *pfnGetMultiPlaneOverlayFilterRange)(void*);
  HRESULT (__stdcall *pfnCheckMultiPlaneOverlaySupport)(DXGI_DDI_ARG_CHECKMULTIPLANEOVERLAYSUPPORT*);
  HRESULT (__stdcall *pfnPresentMultiPlaneOverlay)(DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY*);
} DXGI1_2_DDI_BASE_FUNCTIONS;
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

 


### -field pfnGetMultiplaneOverlayFilterRange

 


### -field pfnCheckMultiplaneOverlaySupport

 


### -field pfnPresentMultiplaneOverlay

 



#### - pfnGetMultiPlaneOverlayCaps

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/dn265493">pfnGetMultiPlaneOverlayCaps</a> function. Supported starting with Windows 8.1.


#### - pfnGetMultiPlaneOverlayFilterRange

This member is reserved and should be set to zero. Supported starting with Windows 8.1.


#### - pfnCheckMultiPlaneOverlaySupport

A pointer to the driver's <a href="https://msdn.microsoft.com/9062BB6D-7B52-42B0-83D9-A101299C0B12">pfnCheckMultiPlaneOverlaySupport (DXGI)</a> function. Supported starting with Windows 8.1.


#### - pfnPresentMultiPlaneOverlay

A pointer to the driver's <a href="..\dxgiddi\nc-dxgiddi-pfnddxgiddi_present_multiplane_overlaycb.md">pfnPresentMultiplaneOverlay (DXGI)</a> function. Supported starting with Windows 8.1.


## -see-also

<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_base_args.md">DXGI_DDI_BASE_ARGS</a>

<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_base_functions.md">DXGI_DDI_BASE_FUNCTIONS</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a>

<a href="..\dxgiddi\ns-dxgiddi-dxgi1_3_ddi_base_functions.md">DXGI1_3_DDI_BASE_FUNCTIONS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI1_2_DDI_BASE_FUNCTIONS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

