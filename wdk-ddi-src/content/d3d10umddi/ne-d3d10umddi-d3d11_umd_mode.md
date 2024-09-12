---
UID: NE:d3d10umddi.D3D11_UMD_MODE
tech.root: display
title: D3D11_UMD_MODE
ms.date: 08/23/2024
targetos: Windows
description: Learn more about the D3D11_UMD_MODE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d10umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D11_UMD_MODE
f1_keywords:
 - D3D11_UMD_MODE
 - d3d10umddi/D3D11_UMD_MODE
dev_langs:
 - c++
helpviewer_keywords:
 - D3D11_UMD_MODE
---

## -description

The **D3D11_UMD_MODE** enumeration specifies the mode that a native D3D11 user-mode driver wants to run in.

## -enum-fields

### -field D3D11_UMD_MODE_NATIVE11

Use the IHV's native D3D11 UMD without enlightment.

### -field D3D11_UMD_MODE_SYSTEM11ON12

Use the version of 11on12 that ships with the operating system.

### -field D3D11_UMD_MODE_VENDOR11ON12

Use the IHV's native D3D11 UMD with 11on12 enlightment.

## -remarks

For more information, see [D3D11On12 open source code](https://github.com/microsoft/D3D11On12).

## -see-also

[**PFND3D11DDI_QUERYDESIREDMODE1**](nc-d3d10umddi-pfnd3d11ddi_querydesiredmode1.md)