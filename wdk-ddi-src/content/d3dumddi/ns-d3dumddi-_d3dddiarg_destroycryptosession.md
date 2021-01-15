---
UID: NS:d3dumddi._D3DDDIARG_DESTROYCRYPTOSESSION
title: _D3DDDIARG_DESTROYCRYPTOSESSION (d3dumddi.h)
description: The D3DDDIARG_DESTROYCRYPTOSESSION structure contains the handle to an encryption session that is destroyed in a call to the DestroyCryptoSession function.
old-location: display\d3dddiarg_destroycryptosession.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_DESTROYCRYPTOSESSION structure"]
ms.keywords: D3DDDIARG_DESTROYCRYPTOSESSION, D3DDDIARG_DESTROYCRYPTOSESSION structure [Display Devices], UMDisplayDriver_param_Structs_75cddfac-f1d8-4378-bb94-441fff43e224.xml, _D3DDDIARG_DESTROYCRYPTOSESSION, d3dumddi/D3DDDIARG_DESTROYCRYPTOSESSION, display.d3dddiarg_destroycryptosession
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DESTROYCRYPTOSESSION is supported beginning with the Windows 7 operating system.
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
req.typenames: D3DDDIARG_DESTROYCRYPTOSESSION
f1_keywords:
 - _D3DDDIARG_DESTROYCRYPTOSESSION
 - d3dumddi/_D3DDDIARG_DESTROYCRYPTOSESSION
 - D3DDDIARG_DESTROYCRYPTOSESSION
 - d3dumddi/D3DDDIARG_DESTROYCRYPTOSESSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDIARG_DESTROYCRYPTOSESSION
 - D3DDDIARG_DESTROYCRYPTOSESSION
---

# _D3DDDIARG_DESTROYCRYPTOSESSION structure


## -description

The D3DDDIARG_DESTROYCRYPTOSESSION structure contains the handle to an encryption session that is destroyed in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_destroycryptosession">DestroyCryptoSession</a> function.

## -struct-fields

### -field hCryptoSession

[in] The handle to the encryption session that the driver destroys.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_destroycryptosession">DestroyCryptoSession</a>

