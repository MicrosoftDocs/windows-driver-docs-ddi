---
UID: NS:d3d10umddi.D3D11_1DDI_D3D11_OPTIONS_DATA
title: D3D11_1DDI_D3D11_OPTIONS_DATA
author: windows-driver-content
description: Specifies options to provide data to the user-mode display driver.
old-location: display\d3d11_1ddi_d3d11_options_data.htm
old-project: display
ms.assetid: de5fa80e-d3bd-40ef-8e4d-07a0a336f25c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDI_D3D11_OPTIONS_DATA, D3D11_1DDI_D3D11_OPTIONS_DATA structure [Display Devices], d3d10umddi/D3D11_1DDI_D3D11_OPTIONS_DATA, display.d3d11_1ddi_d3d11_options_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_D3D11_OPTIONS_DATA
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_D3D11_OPTIONS_DATA
---

# D3D11_1DDI_D3D11_OPTIONS_DATA structure


## -description


Specifies options to provide data to the user-mode display driver.


## -struct-fields




### -field OutputMergerLogicOp

Specifies whether logic operations are available in the blend state. The user-mode display driver sets this member to <b>TRUE</b> if logic operations are available in the blend state and <b>FALSE</b> otherwise. This member is <b>FALSE</b> if the   driver supports Direct3D feature level 9.1, 9.2, and 9.3. This member is optional if the driver supports feature level 10, 10.1, and 11. This member is <b>TRUE</b> if the driver supports feature level 11.1 and later.


### -field AssignDebugBinarySupport

Specifies whether the driver supports the <a href="https://msdn.microsoft.com/eb1e3c27-71c1-4920-9aa4-3253306fa3f4">AssignDebugBinary</a> function, which provides the full shader binary that is available after shader creation.


## -see-also




<a href="https://msdn.microsoft.com/eb1e3c27-71c1-4920-9aa4-3253306fa3f4">AssignDebugBinary</a>
 

 

