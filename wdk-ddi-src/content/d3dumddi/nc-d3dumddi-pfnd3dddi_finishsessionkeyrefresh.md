---
UID: NC:d3dumddi.PFND3DDDI_FINISHSESSIONKEYREFRESH
title: PFND3DDDI_FINISHSESSIONKEYREFRESH (d3dumddi.h)
description: The FinishSessionKeyRefresh function indicates that all buffers from that point in time use the updated session key value.
old-location: display\finishsessionkeyrefresh.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_FINISHSESSIONKEYREFRESH callback function"]
ms.keywords: FinishSessionKeyRefresh, FinishSessionKeyRefresh callback function [Display Devices], PFND3DDDI_FINISHSESSIONKEYREFRESH, PFND3DDDI_FINISHSESSIONKEYREFRESH callback, UserModeDisplayDriver_Functions_6b7be711-8539-4b49-99d0-efbd424b33cc.xml, d3dumddi/FinishSessionKeyRefresh, display.finishsessionkeyrefresh
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: The FinishSessionKeyRefresh function is supported beginning with the Windows 7 operating system.
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
 - PFND3DDDI_FINISHSESSIONKEYREFRESH
 - d3dumddi/PFND3DDDI_FINISHSESSIONKEYREFRESH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - FinishSessionKeyRefresh
product:
 - Windows
---

# PFND3DDDI_FINISHSESSIONKEYREFRESH callback function


## -description

The <i>FinishSessionKeyRefresh</i> function indicates that all buffers from that point in time use the updated session key value.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_finishsessionkeyrefresh">D3DDDIARG_FINISHSESSIONKEYREFRESH</a> structure that describes the session.

## -returns

<i>FinishSessionKeyRefresh</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The session is successfully updated.|
|D3DDDIERR_NOTAVAILABLE|The driver does not support the FinishSessionKeyRefresh function.|

## -remarks

The hardware and driver can optionally support the <i>FinishSessionKeyRefresh</i> function for all crypto types.

When the Direct3D runtime calls the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_startsessionkeyrefresh">StartSessionKeyRefresh</a> function, the driver generates and saves a random number and returns the random number in the buffer that the <b>pRandomNumber</b> member of the <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_startsessionkeyrefresh">D3DDDIARG_STARTSESSIONKEYREFRESH</a> structure points to. 

When the runtime subsequently calls the driver's <i>FinishSessionKeyRefresh</i> function, the driver performs an XOR operation of the random number with the session key.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_finishsessionkeyrefresh">D3DDDIARG_FINISHSESSIONKEYREFRESH</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_startsessionkeyrefresh">D3DDDIARG_STARTSESSIONKEYREFRESH</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_startsessionkeyrefresh">StartSessionKeyRefresh</a>
