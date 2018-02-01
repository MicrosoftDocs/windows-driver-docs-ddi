---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS
title: PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS
author: windows-driver-content
description: CheckCryptoSessionStatus returns the status of a CryptoSession object.
old-location: display\checkcryptosessionstatus.htm
old-project: display
ms.assetid: C7BA5CE0-F89E-4C4B-9976-B9CB6BF8DA81
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.checkcryptosessionstatus, CheckCryptoSessionStatus callback function [Display Devices], CheckCryptoSessionStatus, d3d10umddi/CheckCryptoSessionStatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d10umddi.h
apiname:
-	CheckCryptoSessionStatus
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS callback


## -description


<b>CheckCryptoSessionStatus</b> returns the status of a <b>CryptoSession</b> object.


## -prototype


````
 VOID APIENTRY* CheckCryptoSessionStatus(
  _In_    D3D10DDI_HDEVICE                    hDevice,
  _In_    D3D11_1DDI_HCRYPTOSESSION            hCryptoSession,
  _Inout_ D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS *pStatus
);
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param hCryptoSession [in]

A handle to the cryptographic session object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a>DDI.


### -param *pStatus [in, out]

Receives a status as a value of the <a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm2_0ddi_crypto_session_status.md">D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS</a> enumeration.


## -returns


This callback function does not return a value.



## -remarks


The application may call this DDI after receiving a hardware content protection tear-down notification to determine the state of the underlying hardware key and protected content.



## -see-also

<a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm2_0ddi_crypto_session_status.md">D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

