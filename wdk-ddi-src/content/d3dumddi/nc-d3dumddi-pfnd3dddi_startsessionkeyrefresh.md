---
UID: NC:d3dumddi.PFND3DDDI_STARTSESSIONKEYREFRESH
title: PFND3DDDI_STARTSESSIONKEYREFRESH (d3dumddi.h)
description: The StartSessionKeyRefresh function returns a random number that the driver's FinishSessionKeyRefresh function subsequently uses to perform an exclusive OR operation (XOR) with the session key.
old-location: display\startsessionkeyrefresh.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_STARTSESSIONKEYREFRESH callback function"]
ms.keywords: PFND3DDDI_STARTSESSIONKEYREFRESH, PFND3DDDI_STARTSESSIONKEYREFRESH callback, StartSessionKeyRefresh, StartSessionKeyRefresh callback function [Display Devices], UserModeDisplayDriver_Functions_c68a1081-f350-4439-8c1c-91d9c54469bd.xml, d3dumddi/StartSessionKeyRefresh, display.startsessionkeyrefresh
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: StartSessionKeyRefresh is supported beginning with the Windows 7 operating system.
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
 - PFND3DDDI_STARTSESSIONKEYREFRESH
 - d3dumddi/PFND3DDDI_STARTSESSIONKEYREFRESH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_STARTSESSIONKEYREFRESH
product:
 - Windows
---

# PFND3DDDI_STARTSESSIONKEYREFRESH callback function


## -description

The <i>StartSessionKeyRefresh</i> function returns a random number that the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_finishsessionkeyrefresh">FinishSessionKeyRefresh</a> function subsequently uses to perform an exclusive OR operation (XOR) with the session key.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_startsessionkeyrefresh">D3DDDIARG_STARTSESSIONKEYREFRESH</a> structure that contains information about the random number.

## -returns

<i>StartSessionKeyRefresh</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The random number is successfully returned.|
|D3DDDIERR_NOTAVAILABLE|The driver does not support the StartSessionKeyRefresh function.|

## -remarks

The hardware and driver can optionally support <i>StartSessionKeyRefresh</i> for all crypto types.  

When the Direct3D runtime calls the driver's <i>StartSessionKeyRefresh</i> function, the driver generates and saves a random number and returns the random number in the buffer that the <b>pRandomNumber</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_startsessionkeyrefresh">D3DDDIARG_STARTSESSIONKEYREFRESH</a> structure points to.

When the runtime subsequently calls the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_finishsessionkeyrefresh">FinishSessionKeyRefresh</a> function, the driver performs an XOR operation of the random number with the session key.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_startsessionkeyrefresh">D3DDDIARG_STARTSESSIONKEYREFRESH</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_finishsessionkeyrefresh">FinishSessionKeyRefresh</a>

