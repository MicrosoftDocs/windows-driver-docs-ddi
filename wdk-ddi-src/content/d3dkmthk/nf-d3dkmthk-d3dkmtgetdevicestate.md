---
UID: NF:d3dkmthk.D3DKMTGetDeviceState
title: D3DKMTGetDeviceState function (d3dkmthk.h)
description: The D3DKMTGetDeviceState function retrieves the state of a device.
old-location: display\d3dkmtgetdevicestate.htm
ms.date: 05/10/2018
keywords: ["D3DKMTGetDeviceState function"]
ms.keywords: D3DKMTGetDeviceState, D3DKMTGetDeviceState function [Display Devices], OpenGL_Functions_396da637-bbc6-478c-8ec9-534d82691c45.xml, d3dkmthk/D3DKMTGetDeviceState, display.d3dkmtgetdevicestate
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - D3DKMTGetDeviceState
 - d3dkmthk/D3DKMTGetDeviceState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Gdi32.dll
 - API-MS-Win-dx-d3dkmt-l1-1-0.dll
 - API-MS-Win-dx-d3dkmt-l1-1-1.dll
 - API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
 - D3DKMTGetDeviceState
---

# D3DKMTGetDeviceState function


## -description

The <b>D3DKMTGetDeviceState</b> function retrieves the state of a device.

## -parameters

### -param Arg1

*pData* [in, out]

[in/out] A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_getdevicestate">D3DKMT_GETDEVICESTATE</a> structure that describes parameters for retrieving the state of a device.

## -returns

<b>D3DKMTGetDeviceState</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The state of the device was successfully retrieved.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped or the display device was reset.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_getdevicestate">D3DKMT_GETDEVICESTATE</a>
