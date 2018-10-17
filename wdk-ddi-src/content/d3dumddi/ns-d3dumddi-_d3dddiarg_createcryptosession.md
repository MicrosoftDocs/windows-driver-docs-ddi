---
UID: NS:d3dumddi._D3DDDIARG_CREATECRYPTOSESSION
title: "_D3DDDIARG_CREATECRYPTOSESSION"
author: windows-driver-content
description: The D3DDDIARG_CREATECRYPTOSESSION structure describes an encryption session to create.
old-location: display\d3dddiarg_createcryptosession.htm
tech.root: display
ms.assetid: 45bc4d3f-d573-4a11-8d25-160cb8f233f4
ms.date: 5/10/2018
ms.keywords: D3DDDIARG_CREATECRYPTOSESSION, D3DDDIARG_CREATECRYPTOSESSION structure [Display Devices], UMDisplayDriver_param_Structs_39cf7246-689d-47f2-99f8-dcc3b2018958.xml, _D3DDDIARG_CREATECRYPTOSESSION, d3dumddi/D3DDDIARG_CREATECRYPTOSESSION, display.d3dddiarg_createcryptosession
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_CREATECRYPTOSESSION is supported beginning with the Windows 7 operating system.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIARG_CREATECRYPTOSESSION
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATECRYPTOSESSION
---

# _D3DDDIARG_CREATECRYPTOSESSION structure


## -description


The D3DDDIARG_CREATECRYPTOSESSION structure describes an encryption session to create. 


## -struct-fields




### -field CryptoType

[in] A GUID that indicates the encryption type, which the driver uses for the encryption session that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a> function creates. The GUID can be one of the following:





#### D3DCRYPTOTYPE_AES128_CTR

A GUID that indicates the 128 bit AES-CRT block cipher.



#### D3DCRYPTOTYPE_PROPRIETARY

A GUID that indicates a proprietary encryption algorithm. 


### -field DecodeProfile

 [in] A GUID that indicates the DirectX Video Acceleration (DirectX VA) decode profile that the driver uses for the encryption session that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a> function creates. The driver uses this decode profile in conjunction with the encryption type that the <b>CryptoType</b> member specifies. 


### -field hCryptoSession

[in/out] A handle to the encryption session. The user-mode display driver must set this handle to a value that the Microsoft Direct3D runtime can use to identify the encryption session in subsequent calls. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a>
 

 

