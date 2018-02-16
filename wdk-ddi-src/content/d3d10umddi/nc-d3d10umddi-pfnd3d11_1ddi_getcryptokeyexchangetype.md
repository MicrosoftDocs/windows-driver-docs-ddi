---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETCRYPTOKEYEXCHANGETYPE
title: PFND3D11_1DDI_GETCRYPTOKEYEXCHANGETYPE
author: windows-driver-content
description: Queries the type of key exchange that is supported by the cryptographic engine of the display adapter for a specified encryption algorithm and video decoder profile.
old-location: display\getcryptokeyexchangetype.htm
old-project: display
ms.assetid: 64870c9f-facf-4344-93d0-12cbcec86e11
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.getcryptokeyexchangetype, GetCryptoKeyExchangeType callback function [Display Devices], GetCryptoKeyExchangeType, PFND3D11_1DDI_GETCRYPTOKEYEXCHANGETYPE, PFND3D11_1DDI_GETCRYPTOKEYEXCHANGETYPE, d3d10umddi/GetCryptoKeyExchangeType
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d10umddi.h
apiname:
-	GetCryptoKeyExchangeType
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D11_1DDI_GETCRYPTOKEYEXCHANGETYPE callback


## -description


Queries the type of key exchange that is supported by the cryptographic engine of the display adapter for a specified encryption algorithm and video decoder profile.  


## -prototype


````
PFND3D11_1DDI_GETCRYPTOKEYEXCHANGETYPE GetCryptoKeyExchangeType;

HRESULT APIENTRY* GetCryptoKeyExchangeType(
  _In_        D3D10DDI_HDEVICE hDevice,
  _In_  const GUID             *pCryptoType,
  _In_  const GUID             *pDecodeProfile,
  _In_        UINT             Index,
  _Out_       GUID             *pKeyExchangeType
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param *pCryptoType [in]

A pointer to a GUID that specifies the type of encryption algorithm to query.


### -param *pDecodeProfile [in]

A pointer to a GUID that specifies the decoder profile to query.


### -param Index [in]

The zero-based index of the key exchange type.


### -param *pKeyExchangeType [out]

A pointer to a GUID that specifies the supported key exchange type for the specified index.


## -returns



<b>GetCryptoKeyExchangeType</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The content protection capabilities were queried successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DERR_INVALID_CRYPTO</b></dt>
</dl>
</td>
<td width="60%">
The encryption algorithm specified by the <i>pCryptoType</i> parameter is not supported.

</td>
</tr>
</table>
 




## -remarks



The <b>GetCryptoKeyExchangeType</b> function can be called to query the key exchange types for any index from 0 to (<b>D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS.KeyExchangeTypeCount</b>– 1). 

The <i>pCryptoType</i> parameter can contain one of the following values:

<ul>
<li>
<b>D3DCRYPTOTYPE_AES128_CTR</b> if the driver is configured to use the 128-bit Advanced Encryption Standard CTR mode (AES-CTR) block cipher. 


</li>
<li>
<b>D3DCRYPTOTYPE_PROPRIETARY</b> if the driver is configured to use a proprietary encryption algorithm. 


</li>
<li>
<b>NULL_GUID</b> if the driver is not configured to use any encryption algorithm.

</li>
</ul>
<div class="alert"><b>Note</b>  The Microsoft Direct3D runtime verifies that the  <i>pDecodeProfile</i>, <i>pCryptoType</i>, and <i>Index</i> parameter data is valid before it calls the <i>GetCryptoKeyExchangeType</i> function.</div>
<div> </div>



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcontentprotectioncaps.md">GetContentProtectionCaps</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_content_protection_caps.md">D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_GETCRYPTOKEYEXCHANGETYPE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

