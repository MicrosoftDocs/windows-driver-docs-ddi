---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETENCRYPTIONBLTKEY
title: PFND3D11_1DDI_GETENCRYPTIONBLTKEY
author: windows-driver-content
description: Queries the key that is used to decrypt the data returned by the EncryptionBlt(D3D11_1) function.
old-location: display\getencryptionbltkey1.htm
old-project: display
ms.assetid: f1d3a443-7980-4894-b6a9-04c0886c6996
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PFND3D11_1DDI_GETENCRYPTIONBLTKEY, d3d10umddi/pfnGetEncryptionBltKey, display.getencryptionbltkey1, pfnGetEncryptionBltKey, pfnGetEncryptionBltKey callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8,Available in Windows Desktop version 10.0.10030.0
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	pfnGetEncryptionBltKey
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_GETENCRYPTIONBLTKEY callback


## -description


Queries the key that is used to decrypt the data returned by the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_encryptionblt.md">EncryptionBlt(D3D11_1)</a> function.


## -prototype


````
PFND3D11_1DDI_GETENCRYPTIONBLTKEY pfnGetEncryptionBltKey;

VOID pfnGetEncryptionBltKey(
   D3D10DDI_HDEVICE          hDevice,
   D3D11_1DDI_HCRYPTOSESSION hCryptoSession,
   UINT                      KeySize,
   VOID                      pReadbackKey
)
{ ... }
````


## -parameters




### -param hDevice

A handle to the display device (graphics context).




### -param hCryptoSession

A handle to the cryptographic session that was created in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a> function. 


### -param KeySize

The size, in bytes, of the encryption key that the <i>pReadBackKey</i> parameter points to.


### -param *pReadbackKey

A pointer to a buffer that contains the encryption key.


## -returns



This callback function does not return a value.




## -remarks



When the <b>GetEncryptionBltKey</b> function is called, the display miniport driver should generate a new encryption key.  If the cryptographic session is using  the <b>D3DCRYPTOTYPE_AES128_CTR</b> cryptographic type, the driver or graphics adapter should encrypt the data that is referenced by the   <i>pReadbackKey</i> parameter by using the session key with the AES-ECB algorithm.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_encryptionblt.md">EncryptionBlt(D3D11_1)</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_GETENCRYPTIONBLTKEY callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

