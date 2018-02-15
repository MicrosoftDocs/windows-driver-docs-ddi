---
UID: NC:d3dumddi.PFND3DDDI_DECRYPTIONBLT
title: PFND3DDDI_DECRYPTIONBLT
author: windows-driver-content
description: The DecryptionBlt function writes data to a protected surface.
old-location: display\decryptionblt.htm
old-project: display
ms.assetid: 1bfe2b9c-90f6-48bf-b0b3-30788ef94110
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.decryptionblt, DecryptionBlt callback function [Display Devices], DecryptionBlt, PFND3DDDI_DECRYPTIONBLT, PFND3DDDI_DECRYPTIONBLT, d3dumddi/DecryptionBlt, UserModeDisplayDriver_Functions_6c7efbab-8c07-4953-80cc-4d18080c12cc.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: DecryptionBlt is supported beginning with the Windows 7 operating system.
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
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	DecryptionBlt
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DECRYPTIONBLT callback


## -description


The <b>DecryptionBlt</b> function writes data to a protected surface. 


## -prototype


````
PFND3DDDI_DECRYPTIONBLT DecryptionBlt;

__checkReturn HRESULT APIENTRY DecryptionBlt(
  _In_       HANDLE                  hDevice,
  _In_ const D3DDDIARG_DECRYPTIONBLT *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context). 


### -param *








#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decryptionblt.md">D3DDDIARG_DECRYPTIONBLT</a> structure that describes the parameters of the decrypted bit-block transfer (bitblt) operation. 


## -returns



<b>DecryptionBlt</b> returns one of the following values:

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
The decrypted bitblt operation is successfully performed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decryptionblt.md">DecryptionBlt</a> could not allocate the required memory for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_NOTAVAILABLE</b></dt>
</dl>
</td>
<td width="60%">
The driver does not support the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decryptionblt.md">DecryptionBlt</a> function. 

</td>
</tr>
</table>
 




## -remarks



Hardware and drivers can optionally support <b>DecryptionBlt</b> for some crypto types. 

If the calling application requires the use of a content key, the application uses the content key to encrypt the data, and the session key to encrypt the content key before passing the content key in the block of memory that the <b>pContentKey</b> member of <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decryptionblt.md">D3DDDIARG_DECRYPTIONBLT</a> points to. If <b>pContentKey</b> is <b>NULL</b>, it indicates that the application used the session key to encrypt the data.

If the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a> function previously created the encryption session with the <b>CryptoType</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createcryptosession.md">D3DDDIARG_CREATECRYPTOSESSION</a> structure set to D3DCRYPTOTYPE_AES128_CTR, the <b>pIV</b> member of <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decryptionblt.md">D3DDDIARG_DECRYPTIONBLT</a> points to the <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_pvp_hw_iv.md">DXVADDI_PVP_HW_IV</a> structure and contains the initialization vector that the application used to encrypt the buffer. The driver's <b>DecryptionBlt</b> function should fail if it determines that the initialization vector was previously used for the same content key (or session key if the content key is not used). The application should increment the <b>IV</b> member of the DXVADDI_PVP_HW_IV structure for each buffer that the application encrypts. Therefore, the driver's <b>DecryptionBlt</b> function can fail if the <b>IV</b> member is less than or equal to the previous <b>IV</b> value that was passed to <b>DecryptionBlt</b>.

If the driver and hardware support partially encrypted buffers, the <b>pEncryptedBlockInfo</b> member of <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decryptionblt.md">D3DDDIARG_DECRYPTIONBLT</a> indicates the portions of the buffer that are encrypted and the portions that are not encrypted.  If the entire buffer is encrypted, <b>pEncryptedBlockInfo</b> should be <b>NULL</b>.

<b>DecryptionBlt</b> cannot write sub-rectangles.

The Direct3D runtime verifies that the source surface specified by the <b>SrcSubResourceIndex</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decryptionblt.md">D3DDDIARG_DECRYPTIONBLT</a> structure is in system memory and that no stretching, colorspace conversion, and so on is performed. An application should ensure that the system memory buffer is properly aligned and that the buffer's size matches the destination surface. The driver should verify the memory alignment and the buffer size (<b>SrcResourceSize</b> member of D3DDDIARG_DECRYPTIONBLT) and fail if these conditions are not correct..




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createcryptosession.md">D3DDDIARG_CREATECRYPTOSESSION</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decryptionblt.md">D3DDDIARG_DECRYPTIONBLT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DECRYPTIONBLT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

