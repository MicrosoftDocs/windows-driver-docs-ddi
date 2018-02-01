---
UID: NS:dxgiddi.DXGI_DDI_BASE_FUNCTIONS
title: DXGI_DDI_BASE_FUNCTIONS
author: windows-driver-content
description: The DXGI_DDI_BASE_FUNCTIONS structure contains functions that the user-mode display driver can implement to perform low-level tasks like presenting rendered frames to an output, controlling gamma, and managing a full-screen transition.
old-location: display\dxgi_ddi_base_functions.htm
old-project: display
ms.assetid: c9fd9b21-4338-4633-903f-308763cbc301
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: UMDisplayDriver_Dx10param_Structs_f33992c1-f203-4058-a6c4-844b2ff8ffa9.xml, dxgiddi/DXGI_DDI_BASE_FUNCTIONS, display.dxgi_ddi_base_functions, DXGI_DDI_BASE_FUNCTIONS structure [Display Devices], DXGI_DDI_BASE_FUNCTIONS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
-	HeaderDef
apilocation:
-	dxgiddi.h
apiname:
-	DXGI_DDI_BASE_FUNCTIONS
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_BASE_FUNCTIONS
---

# DXGI_DDI_BASE_FUNCTIONS structure


## -description


The DXGI_DDI_BASE_FUNCTIONS structure contains functions that the user-mode display driver can implement to perform low-level tasks like presenting rendered frames to an output, controlling gamma, and managing a full-screen transition.


## -syntax


````
typedef struct DXGI_DDI_BASE_FUNCTIONS {
  HRESULT (__stdcall *pfnPresent)(DXGI_DDI_ARG_PRESENT*);
  HRESULT (__stdcall *pfnGetGammaCaps)(DXGI_DDI_ARG_GET_GAMMA_CONTROL_CAPS*);
  HRESULT (__stdcall *pfnSetDisplayMode)(DXGI_DDI_ARG_SETDISPLAYMODE*);
  HRESULT (__stdcall *pfnSetResourcePriority)(DXGI_DDI_ARG_SETRESOURCEPRIORITY*);
  HRESULT (__stdcall *pfnQueryResourceResidency)(DXGI_DDI_ARG_QUERYRESOURCERESIDENCY*);
  HRESULT (__stdcall *pfnRotateResourceIdentities)(DXGI_DDI_ARG_ROTATE_RESOURCE_IDENTITIES*);
  HRESULT (__stdcall *pfnBlt)(DXGI_DDI_ARG_BLT*);
} DXGI_DDI_BASE_FUNCTIONS;
````


## -struct-fields




### -field pfnPresent

A pointer to the driver's  <a href="https://msdn.microsoft.com/library/windows/hardware/ff569179">PresentDXGI</a> function.


### -field pfnGetGammaCaps

A pointer to the driver's  <a href="https://msdn.microsoft.com/library/windows/hardware/ff566790">GetGammaCapsDXGI</a> function.


### -field pfnSetDisplayMode

A pointer to the driver's  <a href="https://msdn.microsoft.com/library/windows/hardware/ff569536">SetDisplayModeDXGI</a> function.


### -field pfnSetResourcePriority

A pointer to the driver's  <a href="https://msdn.microsoft.com/library/windows/hardware/ff569657">SetResourcePriorityDXGI</a> function.


### -field pfnQueryResourceResidency

A pointer to the driver's  <a href="https://msdn.microsoft.com/library/windows/hardware/ff569224">QueryResourceResidencyDXGI</a> function.


### -field pfnRotateResourceIdentities

A pointer to the driver's  <a href="https://msdn.microsoft.com/library/windows/hardware/ff569514">RotateResourceIdentitiesDXGI</a> function.


### -field pfnBlt

A pointer to the driver's  <a href="https://msdn.microsoft.com/library/windows/hardware/ff538252">BltDXGI</a> function.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566790">GetGammaCapsDXGI</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538252">BltDXGI</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569657">SetResourcePriorityDXGI</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569179">PresentDXGI</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569536">SetDisplayModeDXGI</a>

<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_base_args.md">DXGI_DDI_BASE_ARGS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569224">QueryResourceResidencyDXGI</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569514">RotateResourceIdentitiesDXGI</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_BASE_FUNCTIONS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

