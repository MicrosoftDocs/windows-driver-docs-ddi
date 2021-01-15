---
UID: NC:d3dumddi.PFND3DDDI_GETINFO
title: PFND3DDDI_GETINFO (d3dumddi.h)
description: The GetInfo function retrieves information about the specified display device.
old-location: display\getinfo.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_GETINFO callback function"]
ms.keywords: GetInfo, GetInfo callback function [Display Devices], PFND3DDDI_GETINFO, PFND3DDDI_GETINFO callback, UserModeDisplayDriver_Functions_21bbab23-9804-468e-80fb-6618f8356ac7.xml, d3dumddi/GetInfo, display.getinfo
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFND3DDDI_GETINFO
 - d3dumddi/PFND3DDDI_GETINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_GETINFO
product:
 - Windows
---

# PFND3DDDI_GETINFO callback function


## -description

The <i>GetInfo</i> function retrieves information about the specified display device.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*DevInfoID*

An identifier for the type of device information to retrieve.

### -param Arg3

*pDevInfoStruct*

A pointer to a buffer of the type that <i>DevInfoID</i> specifies that receives information about the device.

### -param DevInfoSize

The size, in bytes, of the buffer that is supplied by <i>pDevInfoStruct</i>.

## -returns

<i>GetInfo</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The device information is successfully retrieved.|
|E_NOTIMPL|The driver does not support the requested type of device information.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|

## -remarks

The Microsoft DirectX 7 and DirectX 8 runtimes call the <i>GetInfo</i> function to query a user-mode display driver for additional device information.

The Direct3D 8 runtime sets the D3DDDIDEVINFOID_VCACHE flag in the <i>DevInfoID</i> parameter and specifies an empty <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddidevinfo_vcache">D3DDDIDEVINFO_VCACHE</a> structure in the <i>pDevInfoStruct</i> parameter to query the user-mode display driver's support for vertex cache.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddidevinfo_vcache">D3DDDIDEVINFO_VCACHE</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

