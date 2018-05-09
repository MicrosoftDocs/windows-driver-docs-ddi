---
UID: NS:dxgiddi.DXGI_DDI_BASE_ARGS
title: DXGI_DDI_BASE_ARGS
author: windows-driver-content
description: The DXGI_DDI_BASE_ARGS structure contains Microsoft DirectX Graphics Infrastructure (DXGI) basic device driver interface (DDI) device creation arguments.
old-location: display\dxgi_ddi_base_args.htm
old-project: display
ms.assetid: e835edb9-7a7e-4258-957a-49877b1ed562
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGI_DDI_BASE_ARGS, DXGI_DDI_BASE_ARGS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_3dec4197-80df-4de3-96ca-d4f90f23e85d.xml, display.dxgi_ddi_base_args, dxgiddi/DXGI_DDI_BASE_ARGS
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dxgiddi.h
api_name:
-	DXGI_DDI_BASE_ARGS
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_BASE_ARGS
---

# DXGI_DDI_BASE_ARGS structure


## -description


The <b>DXGI_DDI_BASE_ARGS</b> structure contains Microsoft DirectX Graphics Infrastructure (DXGI) basic device driver interface (DDI) device creation arguments.


## -struct-fields




### -field pDXGIBaseCallbacks

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557487">DXGI_DDI_BASE_CALLBACKS</a> structure that contains a table of Microsoft Direct3D runtime callback functions that the driver can use to access kernel services.


### -field pDXGIDDIBaseFunctions6_1

 


### -field pDXGIDDIBaseFunctions6

 


### -field pDXGIDDIBaseFunctions5

 


### -field pDXGIDDIBaseFunctions4

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn465883">DXGI1_3_DDI_BASE_FUNCTIONS</a> structure that the user-mode display driver fills with a table of its functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

 Supported starting with Windows 8.1.


### -field pDXGIDDIBaseFunctions3

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451215">DXGI1_2_DDI_BASE_FUNCTIONS</a> structure that the user-mode display driver fills with a table of its functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

Supported starting with Windows 8.


### -field pDXGIDDIBaseFunctions2

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557439">DXGI1_1_DDI_BASE_FUNCTIONS</a> structure that the user-mode display driver fills with a table of its functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver.

 Supported starting with Windows 7.


### -field pDXGIDDIBaseFunctions

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557492">DXGI_DDI_BASE_FUNCTIONS</a> structure that the user-mode display driver fills with a table of its functions. The Direct3D runtime uses these functions to communicate with the user-mode display driver.


## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557439">DXGI1_1_DDI_BASE_FUNCTIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451215">DXGI1_2_DDI_BASE_FUNCTIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn465883">DXGI1_3_DDI_BASE_FUNCTIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557487">DXGI_DDI_BASE_CALLBACKS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557492">DXGI_DDI_BASE_FUNCTIONS</a>
 

 

