---
UID: NC:d3d10umddi.PFND3D11_1DDI_STARTSESSIONKEYREFRESH
title: PFND3D11_1DDI_STARTSESSIONKEYREFRESH (d3d10umddi.h)
description: Gets a random number that can be used to refresh the session key.
old-location: display\startsessionkeyrefresh1.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_STARTSESSIONKEYREFRESH callback function"]
ms.keywords: PFND3D11_1DDI_STARTSESSIONKEYREFRESH, PFND3D11_1DDI_STARTSESSIONKEYREFRESH callback, d3d10umddi/pfnStartSessionKeyRefresh, display.startsessionkeyrefresh1, pfnStartSessionKeyRefresh, pfnStartSessionKeyRefresh callback function [Display Devices]
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
 - PFND3D11_1DDI_STARTSESSIONKEYREFRESH
 - d3d10umddi/PFND3D11_1DDI_STARTSESSIONKEYREFRESH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3D11_1DDI_STARTSESSIONKEYREFRESH
product:
 - Windows
---

# PFND3D11_1DDI_STARTSESSIONKEYREFRESH callback function


## -description

Gets a random number that can be used to refresh the session key.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param hCryptoSession

A handle to the cryptographic session object that was created through a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a> function.

### -param RandomNumberSize

The size, in bytes, of the number in the buffer that is referenced by the <i>pRandomNumber</i> parameter.

### -param pRandomNumber

A pointer to a buffer that contains the status sequence number for the random start.

## -remarks

The hardware and driver can optionally support <b>StartSessionKeyRefresh</b> for all cryptographic types.



When the Microsoft Direct3D runtime calls the driver's <b>StartSessionKeyRefresh</b> function, the driver generates and saves a random number and returns it in the buffer that the <i>pRandomNumber</i> parameter points to.

When the runtime subsequently calls the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_finishsessionkeyrefresh">FinishSessionKeyRefresh</a> function, the driver refreshes the session key by performing an XOR operation of the random number with the key.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_finishsessionkeyrefresh">FinishSessionKeyRefresh</a>

