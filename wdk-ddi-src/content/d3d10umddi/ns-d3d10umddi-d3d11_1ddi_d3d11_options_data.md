---
UID: NS:d3d10umddi.D3D11_1DDI_D3D11_OPTIONS_DATA
title: D3D11_1DDI_D3D11_OPTIONS_DATA (d3d10umddi.h)
description: Specifies options to provide data to the user-mode display driver.
old-location: display\d3d11_1ddi_d3d11_options_data.htm
ms.assetid: de5fa80e-d3bd-40ef-8e4d-07a0a336f25c
ms.date: 05/10/2018
ms.keywords: D3D11_1DDI_D3D11_OPTIONS_DATA, D3D11_1DDI_D3D11_OPTIONS_DATA structure [Display Devices], d3d10umddi/D3D11_1DDI_D3D11_OPTIONS_DATA, display.d3d11_1ddi_d3d11_options_data
f1_keywords:
 - "d3d10umddi/D3D11_1DDI_D3D11_OPTIONS_DATA"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3D11_1DDI_D3D11_OPTIONS_DATA
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_D3D11_OPTIONS_DATA
---

# D3D11_1DDI_D3D11_OPTIONS_DATA structure


## -description


Specifies options to provide data to the user-mode display driver.


## -struct-fields




### -field OutputMergerLogicOp

Specifies whether logic operations are available in the blend state. The user-mode display driver sets this member to <b>TRUE</b> if logic operations are available in the blend state and <b>FALSE</b> otherwise. This member is <b>FALSE</b> if the   driver supports Direct3D feature level 9.1, 9.2, and 9.3. This member is optional if the driver supports feature level 10, 10.1, and 11. This member is <b>TRUE</b> if the driver supports feature level 11.1 and later.


### -field AssignDebugBinarySupport

Specifies whether the driver supports the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_assigndebugbinary">AssignDebugBinary</a> function, which provides the full shader binary that is available after shader creation.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_assigndebugbinary">AssignDebugBinary</a>
 

 

