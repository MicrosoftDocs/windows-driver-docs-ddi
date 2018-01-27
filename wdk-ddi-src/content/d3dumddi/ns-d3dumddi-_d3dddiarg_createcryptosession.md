---
UID: NS:d3dumddi._D3DDDIARG_CREATECRYPTOSESSION
title: _D3DDDIARG_CREATECRYPTOSESSION
author: windows-driver-content
description: The D3DDDIARG_CREATECRYPTOSESSION structure describes an encryption session to create.
old-location: display\d3dddiarg_createcryptosession.htm
old-project: display
ms.assetid: 45bc4d3f-d573-4a11-8d25-160cb8f233f4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: UMDisplayDriver_param_Structs_39cf7246-689d-47f2-99f8-dcc3b2018958.xml, D3DDDIARG_CREATECRYPTOSESSION, display.d3dddiarg_createcryptosession, D3DDDIARG_CREATECRYPTOSESSION structure [Display Devices], _D3DDDIARG_CREATECRYPTOSESSION, d3dumddi/D3DDDIARG_CREATECRYPTOSESSION
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	d3dumddi.h
apiname: 
-	D3DDDIARG_CREATECRYPTOSESSION
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATECRYPTOSESSION
---

# _D3DDDIARG_CREATECRYPTOSESSION structure


## -description


The D3DDDIARG_CREATECRYPTOSESSION structure describes an encryption session to create. 


## -syntax


````
typedef struct _D3DDDIARG_CREATECRYPTOSESSION {
  GUID   CryptoType;
  GUID   DecodeProfile;
  HANDLE hCryptoSession;
} D3DDDIARG_CREATECRYPTOSESSION;
````


## -struct-fields




### -field CryptoType

[in] A GUID that indicates the encryption type, which the driver uses for the encryption session that the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a> function creates. The GUID can be one of the following:




### -field DecodeProfile

 [in] A GUID that indicates the DirectX Video Acceleration (DirectX VA) decode profile that the driver uses for the encryption session that the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a> function creates. The driver uses this decode profile in conjunction with the encryption type that the <b>CryptoType</b> member specifies. 


### -field hCryptoSession

[in/out] A handle to the encryption session. The user-mode display driver must set this handle to a value that the Microsoft Direct3D runtime can use to identify the encryption session in subsequent calls. 


##### - CryptoType.D3DCRYPTOTYPE_PROPRIETARY

A GUID that indicates a proprietary encryption algorithm. 


##### - CryptoType.D3DCRYPTOTYPE_AES128_CTR

A GUID that indicates the 128 bit AES-CRT block cipher.


## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_CREATECRYPTOSESSION structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

