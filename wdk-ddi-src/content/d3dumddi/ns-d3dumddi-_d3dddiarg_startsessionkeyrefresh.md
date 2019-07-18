---
UID: NS:d3dumddi._D3DDDIARG_STARTSESSIONKEYREFRESH
title: _D3DDDIARG_STARTSESSIONKEYREFRESH (d3dumddi.h)
description: The D3DDDIARG_STARTSESSIONKEYREFRESH structure contains information about the random number for the encryption session.
old-location: display\d3dddiarg_startsessionkeyrefresh.htm
tech.root: display
ms.assetid: f7494ea8-e639-4466-9d56-07d164f57b5b
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_STARTSESSIONKEYREFRESH, D3DDDIARG_STARTSESSIONKEYREFRESH structure [Display Devices], UMDisplayDriver_param_Structs_63d20fb4-b769-45bf-8e3f-badb7b8e52e2.xml, _D3DDDIARG_STARTSESSIONKEYREFRESH, d3dumddi/D3DDDIARG_STARTSESSIONKEYREFRESH, display.d3dddiarg_startsessionkeyrefresh
ms.topic: struct
f1_keywords:
 - "d3dumddi/D3DDDIARG_STARTSESSIONKEYREFRESH"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_STARTSESSIONKEYREFRESH is supported beginning with the Windows 7 operating system.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDIARG_STARTSESSIONKEYREFRESH
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_STARTSESSIONKEYREFRESH
---

# _D3DDDIARG_STARTSESSIONKEYREFRESH structure


## -description


The D3DDDIARG_STARTSESSIONKEYREFRESH structure contains information about the random number for the encryption session. 


## -struct-fields




### -field hCryptoSession

[in] A handle to the encryption session that is created in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a> function. 


### -field pRandomNumber

[out] A pointer to a buffer that contains the status sequence number for the random start. 


### -field RandomNumberSize

[in/out] The size, in bytes, of the number that the <b>pRandomNumber</b> member points to. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a>
 

 

