---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS
title: PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS
author: windows-driver-content
description: Queries the available content protection for a specified encryption algorithm and video decoder profile.
old-location: display\getcontentprotectioncaps.htm
tech.root: display
ms.assetid: 51024d63-f58c-45a7-bd6f-9f24a6805878
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS, PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS callback, d3d10umddi/pfnGetContentProtectionCaps, display.getcontentprotectioncaps, pfnGetContentProtectionCaps, pfnGetContentProtectionCaps callback function [Display Devices]
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
-	pfnGetContentProtectionCaps
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS callback function


## -description


Queries the available content protection for a specified encryption algorithm and video decoder profile.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param *pCryptoType [in]

A pointer to a GUID that specifies the type of encryption algorithm to query.


### -param *pDecodeProfile [in]

A pointer to a GUID that specifies the decoder profile to query.


### -param *pCaps [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450936">D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS</a> structure that contains the protection capabilities for the specified encryption algorithm and decoder profile.


## -returns



<b>GetContentProtectionCaps</b> returns one of the following values:

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
<div class="alert"><b>Note</b>  The Microsoft Direct3D runtime verifies that the  <i>pDecodeProfile</i> and <i>pCryptoType</i> parameter data is valid before it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451656">GetContentProtectionCaps</a> function.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450936">D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS</a>
 

 

