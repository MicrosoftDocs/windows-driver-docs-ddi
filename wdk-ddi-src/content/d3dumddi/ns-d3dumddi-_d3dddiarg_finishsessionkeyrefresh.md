---
UID: NS:d3dumddi._D3DDDIARG_FINISHSESSIONKEYREFRESH
title: _D3DDDIARG_FINISHSESSIONKEYREFRESH (d3dumddi.h)
description: The D3DDDIARG_FINISHSESSIONKEYREFRESH structure contains the handle to an encryption session to end in a call to the FinishSessionKeyRefresh function.
old-location: display\d3dddiarg_finishsessionkeyrefresh.htm
tech.root: display
ms.assetid: 5d262012-c4f4-4f86-a3a2-48c2fd7d5216
ms.date: 05/10/2018
keywords: ["D3DDDIARG_FINISHSESSIONKEYREFRESH structure"]
ms.keywords: D3DDDIARG_FINISHSESSIONKEYREFRESH, D3DDDIARG_FINISHSESSIONKEYREFRESH structure [Display Devices], UMDisplayDriver_param_Structs_ac18e377-42c2-4c4a-9625-1b0bf29375c2.xml, _D3DDDIARG_FINISHSESSIONKEYREFRESH, d3dumddi/D3DDDIARG_FINISHSESSIONKEYREFRESH, display.d3dddiarg_finishsessionkeyrefresh
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_FINISHSESSIONKEYREFRESH is supported beginning with the Windows 7 operating system.
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
req.typenames: D3DDDIARG_FINISHSESSIONKEYREFRESH
f1_keywords:
 - _D3DDDIARG_FINISHSESSIONKEYREFRESH
 - d3dumddi/_D3DDDIARG_FINISHSESSIONKEYREFRESH
 - D3DDDIARG_FINISHSESSIONKEYREFRESH
 - d3dumddi/D3DDDIARG_FINISHSESSIONKEYREFRESH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_FINISHSESSIONKEYREFRESH
---

# _D3DDDIARG_FINISHSESSIONKEYREFRESH structure


## -description

The D3DDDIARG_FINISHSESSIONKEYREFRESH structure contains the handle to an encryption session to end in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_finishsessionkeyrefresh">FinishSessionKeyRefresh</a> function.

## -struct-fields

### -field hCryptoSession

[in] The handle to the encryption session to end.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_finishsessionkeyrefresh">FinishSessionKeyRefresh</a>