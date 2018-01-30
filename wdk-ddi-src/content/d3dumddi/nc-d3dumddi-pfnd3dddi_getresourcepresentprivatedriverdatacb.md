---
UID: NC:d3dumddi.PFND3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATACB
title: PFND3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATACB
author: windows-driver-content
description: pfnGetResourcePresentPrivateDriverDataCb is used to query the resource private data, which is associated with the resource during Present.
old-location: display\pfngetresourcepresentprivatedriverdatacb.htm
old-project: display
ms.assetid: D4F0F272-60DC-4060-9762-3DB49236CE62
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfngetresourcepresentprivatedriverdatacb, pfnGetResourcePresentPrivateDriverDataCb callback function [Display Devices], pfnGetResourcePresentPrivateDriverDataCb, PFND3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATACB, PFND3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATACB, d3dumddi/pfnGetResourcePresentPrivateDriverDataCb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	pfnGetResourcePresentPrivateDriverDataCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATACB callback


## -description


<b>pfnGetResourcePresentPrivateDriverDataCb</b> is used to query the resource private data, which is associated with the resource during Present. 



## -prototype


````
PFND3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATACB pfnGetResourcePresentPrivateDriverDataCb;

HRESULT APIENTRY CALLBACK* pfnGetResourcePresentPrivateDriverDataCb(
  _In_    HANDLE                                     hDevice,
  _Inout_ D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device.


### -param *






#### - pData [in, out]

A pointer to a <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_getresourcepresentprivatedriverdata.md">D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA</a> structure that describes the operation to perform and contains the results.




## -returns


<table>
<tr>
<th>Return value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>S_OK</dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_INVALID_BUFFER_SIZE</dt>
</dl>
</td>
<td width="60%">
The value of <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_getresourcepresentprivatedriverdata.md">D3DDDI_GETRESOURCEPRESENTPRIVATEDRIVERDATA</a>::<b>PrivateDriverDataSize</b> was zero or was insufficient to hold the data. When control returns to the caller, <b>PrivateDriverDataSize</b> will contain the required buffer size.

</td>
</tr>
</table> 

This method may return other <b>HRESULT</b> values.


