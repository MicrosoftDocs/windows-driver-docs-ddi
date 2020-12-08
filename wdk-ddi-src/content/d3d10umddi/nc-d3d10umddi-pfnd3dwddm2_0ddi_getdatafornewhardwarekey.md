---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY
title: PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY (d3d10umddi.h)
description: Allows the driver to return independent hardware vendor (IHV)-specific information used when initializing the new hardware key.
old-location: display\getdatafornewhardwarekey.htm
ms.date: 05/10/2018
keywords: ["PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY callback function"]
ms.keywords: PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY, PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY callback, d3d10umddi/pfnGetDataForNewHardwareKey, display.getdatafornewhardwarekey, pfnGetDataForNewHardwareKey, pfnGetDataForNewHardwareKey callback function [Display Devices]
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
 - PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY
 - d3d10umddi/PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnGetDataForNewHardwareKey
product:
 - Windows
---

# PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY callback function


## -description

Allows the driver to return independent hardware vendor (IHV)-specific information used when initializing the new hardware key.

## -parameters

### -param hDevice

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a> structure at device creation.

### -param hCryptoSession

A handle to the cryptographic session object that was created through a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a> function.

### -param PrivateInputSize

The size of the  buffer pointed to by <b>pPrivatInputData</b>, in bytes.

### -param pPrivatInputData

A pointer to a buffer that receives private input data for the driver.

### -param pPrivateOutputData

A pointer to a UINT64 value that receives private driver output data that could be used later by the secure DRM component when initializing the key.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|Private driver data was successfully returned.|
|E_OUTOFMEMORY|Memory was not available to complete the operation.|

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a>
