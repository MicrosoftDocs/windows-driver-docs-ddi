---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS
title: PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS
author: windows-driver-content
description: CheckCryptoSessionStatus returns the status of a CryptoSession object.
old-location: display\checkcryptosessionstatus.htm
tech.root: display
ms.assetid: C7BA5CE0-F89E-4C4B-9976-B9CB6BF8DA81
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: CheckCryptoSessionStatus, CheckCryptoSessionStatus callback function [Display Devices], PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS, PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS callback, d3d10umddi/CheckCryptoSessionStatus, display.checkcryptosessionstatus
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	CheckCryptoSessionStatus
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS callback function


## -description


<b>CheckCryptoSessionStatus</b> returns the status of a <b>CryptoSession</b> object.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param hCryptoSession [in]

A handle to the cryptographic session object that was created through a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a>DDI.


### -param *pStatus [in, out]

Receives a status as a value of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn894606">D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS</a> enumeration.


## -returns



This callback function does not return a value.




## -remarks



The application may call this DDI after receiving a hardware content protection tear-down notification to determine the state of the underlying hardware key and protected content.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn894606">D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS</a>
 

 

