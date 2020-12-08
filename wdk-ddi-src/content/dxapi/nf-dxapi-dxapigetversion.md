---
UID: NF:dxapi.DxApiGetVersion
title: DxApiGetVersion function (dxapi.h)
description: Do not use the DxApiGetVersion function; use the DxApi function along with the DD_DXAPI_GETVERSIONNUMBER function identifier instead.The DxApiGetVersion function returns a Direct Sound version number of 4.02.
old-location: display\dxapigetversion.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DxApiGetVersion function"]
ms.keywords: DxApiGetVersion, DxApiGetVersion function [Display Devices], ddfncs_72fbedfa-d63f-462a-a6c4-862c6815f1c1.xml, display.dxapigetversion, dxapi/DxApiGetVersion
req.header: dxapi.h
req.include-header: Dxapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: Dxapi.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - DxApiGetVersion
 - dxapi/DxApiGetVersion
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Dxapi.lib
 - Dxapi.dll
api_name:
 - DxApiGetVersion
---

# DxApiGetVersion function


## -description

Do not use the <b>DxApiGetVersion</b> function; use the <a href="/windows-hardware/drivers/ddi/dxapi/nf-dxapi-dxapi">DxApi</a> function along with the <a href="/previous-versions/windows/hardware/drivers/ff550637(v=vs.85)">DD_DXAPI_GETVERSIONNUMBER</a> function identifier instead.

The <b>DxApiGetVersion</b> function returns a Direct Sound version number of 4.02.

## -returns

Returns the major and minor version numbers of Direct Sound as 4 and 2 respectively.

## -see-also

<a href="/windows/win32/api/ddkmapi/ns-ddkmapi-ddgetversionnumber">DDGETVERSIONNUMBER</a>



<a href="/previous-versions/windows/hardware/drivers/ff550637(v=vs.85)">DD_DXAPI_GETVERSIONNUMBER</a>



<a href="/windows-hardware/drivers/ddi/dxapi/nf-dxapi-dxapi">DxApi</a>
