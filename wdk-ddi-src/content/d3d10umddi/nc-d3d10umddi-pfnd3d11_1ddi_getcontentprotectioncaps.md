---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS
title: PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS
author: windows-driver-content
description: Queries the available content protection for a specified encryption algorithm and video decoder profile.
old-location: display\getcontentprotectioncaps.htm
old-project: display
ms.assetid: 51024d63-f58c-45a7-bd6f-9f24a6805878
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.getcontentprotectioncaps, pfnGetContentProtectionCaps callback function [Display Devices], pfnGetContentProtectionCaps, PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS, PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS, d3d10umddi/pfnGetContentProtectionCaps
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
-	pfnGetContentProtectionCaps
product: Windows
targetos: Windows
req.typenames: "*PPOWERSOURCEUPDATEEX, POWERSOURCEUPDATEEX"
---

# PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS callback


## -description


Queries the available content protection for a specified encryption algorithm and video decoder profile.


## -prototype


````
PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS pfnGetContentProtectionCaps;

HRESULT APIENTRY* pfnGetContentProtectionCaps(
  _In_        D3D10DDI_HDEVICE                         hDevice,
  _In_  const GUID                                     *pCryptoType,
  _In_  const GUID                                     *pDecodeProfile,
  _Out_       D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS *pCaps
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param *pCryptoType



### -param *pDecodeProfile



### -param *pCaps






#### - pCryptoType [in]

A pointer to a GUID that specifies the type of encryption algorithm to query.


#### - pDecodeProfile [in]

A pointer to a GUID that specifies the decoder profile to query.


#### - pCaps [out]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_content_protection_caps.md">D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS</a> structure that contains the protection capabilities for the specified encryption algorithm and decoder profile.


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
</ul><div class="alert"><b>Note</b>  The Microsoft Direct3D runtime verifies that the  <i>pDecodeProfile</i> and <i>pCryptoType</i> parameter data is valid before it calls the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcapturehandle.md">GetContentProtectionCaps</a> function.</div><div> </div>


## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_content_protection_caps.md">D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_GETCONTENTPROTECTIONCAPS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

