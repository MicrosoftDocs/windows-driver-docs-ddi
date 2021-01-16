---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE
title: PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE (d3d10umddi.h)
description: Returns the number of bytes that the driver requires to store private data for the cryptographic session state.
old-location: display\calcprivatecryptosessionsize.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE callback function"]
ms.keywords: CalcPrivateCryptoSessionSize, CalcPrivateCryptoSessionSize callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE, PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE callback, d3d10umddi/CalcPrivateCryptoSessionSize, display.calcprivatecryptosessionsize
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE
 - d3d10umddi/PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE
product:
 - Windows
---

# PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE callback function


## -description

Returns the number of bytes that the driver requires to store private data for the cryptographic session state.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param pCreateData

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createcryptosession">D3D11_1DDIARG_CREATECRYPTOSESSION</a> structure that describes the cryptographic session.

## -returns

The required number of bytes for the cryptographic session state.

## -remarks

The runtime will validate the members of the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createcryptosession">D3D11_1DDIARG_CREATECRYPTOSESSION</a> structure before it calls this function.

This function is not expected to fail.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createcryptosession">D3D11_1DDIARG_CREATECRYPTOSESSION</a>

