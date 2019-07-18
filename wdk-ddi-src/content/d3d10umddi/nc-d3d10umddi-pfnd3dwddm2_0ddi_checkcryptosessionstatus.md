---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS
title: PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS (d3d10umddi.h)
description: CheckCryptoSessionStatus returns the status of a CryptoSession object.
old-location: display\checkcryptosessionstatus.htm
ms.assetid: C7BA5CE0-F89E-4C4B-9976-B9CB6BF8DA81
ms.date: 05/10/2018
ms.keywords: CheckCryptoSessionStatus, CheckCryptoSessionStatus callback function [Display Devices], PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS, PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS callback, d3d10umddi/CheckCryptoSessionStatus, display.checkcryptosessionstatus
ms.topic: callback
f1_keywords:
 - "d3d10umddi/CheckCryptoSessionStatus"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d10umddi.h
api_name:
- CheckCryptoSessionStatus
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS callback function


## -description


<b>CheckCryptoSessionStatus</b> returns the status of a <b>CryptoSession</b> object.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param hCryptoSession [in]

A handle to the cryptographic session object that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a>DDI.


### -param *pStatus [in, out]

Receives a status as a value of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3dwddm2_0ddi_crypto_session_status">D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS</a> enumeration.


## -returns



This callback function does not return a value.




## -remarks



The application may call this DDI after receiving a hardware content protection tear-down notification to determine the state of the underlying hardware key and protected content.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ne-d3d10umddi-d3dwddm2_0ddi_crypto_session_status">D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS</a>
 

 

