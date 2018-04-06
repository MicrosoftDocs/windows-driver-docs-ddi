---
UID: NC:d3d10umddi.PFND3D11_1DDI_DESTROYCRYPTOSESSION
title: PFND3D11_1DDI_DESTROYCRYPTOSESSION
author: windows-driver-content
description: Releases resources for the cryptographic session that were created through a call to the CreateCryptoSession function.
old-location: display\destroycryptosession1.htm
old-project: display
ms.assetid: 067eeba4-2914-4616-98c8-f163cbe5fae2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D11_1DDI_DESTROYCRYPTOSESSION, d3d10umddi/pfnDestroyCryptoSession, display.destroycryptosession1, display.pfndestroycryptosession1, pfnDestroyCryptoSession, pfnDestroyCryptoSession callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	pfnDestroyCryptoSession
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_DESTROYCRYPTOSESSION callback


## -description


Releases resources for the cryptographic session that were created through a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a> function.



## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param hCryptoSession [in]

A handle to the driver's private data for the cryptographic session. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a>.


## -returns



This callback function does not return a value.



