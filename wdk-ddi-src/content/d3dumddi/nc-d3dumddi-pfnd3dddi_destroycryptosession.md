---
UID: NC:d3dumddi.PFND3DDDI_DESTROYCRYPTOSESSION
title: PFND3DDDI_DESTROYCRYPTOSESSION (d3dumddi.h)
description: The DestroyCryptoSession function releases resources for the encryption session that the CreateCryptoSession function creates.
old-location: display\destroycryptosession.htm
tech.root: display
ms.assetid: 4035ef73-e1a2-49e4-808d-c40c980393a4
ms.date: 05/10/2018
ms.keywords: DestroyCryptoSession, DestroyCryptoSession callback function [Display Devices], PFND3DDDI_DESTROYCRYPTOSESSION, PFND3DDDI_DESTROYCRYPTOSESSION callback, UserModeDisplayDriver_Functions_c1fa988d-a8b7-4538-94cd-d364873f4216.xml, d3dumddi/DestroyCryptoSession, display.destroycryptosession
ms.topic: callback
f1_keywords:
 - "d3dumddi/DestroyCryptoSession"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: DestroyCryptoSession is supported beginning with the Windows 7 operating system.
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
- UserDefined
api_location:
- d3dumddi.h
api_name:
- DestroyCryptoSession
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DESTROYCRYPTOSESSION callback function


## -description


The <b>DestroyCryptoSession</b> function releases resources for the encryption session that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a> function creates. 


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_destroycryptosession">D3DDDIARG_DESTROYCRYPTOSESSION</a> structure that contains one member that specifies the handle to the encryption session to destroy. 


## -returns



<b>DestroyCryptoSession</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The encryption session is successfully destroyed.|
|E_OUTOFMEMORY|DestroyCryptoSession could not allocate the required memory for it to complete.|
 
## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_destroycryptosession">D3DDDIARG_DESTROYCRYPTOSESSION</a>
 

 

