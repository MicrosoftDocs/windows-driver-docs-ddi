---
UID: NC:d3dumddi.PFND3DDDI_CRYPTOSESSIONKEYEXCHANGE
title: PFND3DDDI_CRYPTOSESSIONKEYEXCHANGE
author: windows-driver-content
description: The CryptoSessionKeyExchange function negotiates a session key.
old-location: display\cryptosessionkeyexchange.htm
old-project: display
ms.assetid: f8055bb3-b8f1-47f5-9ae0-8e7a26989871
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: CryptoSessionKeyExchange is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CryptoSessionKeyExchange
req.alt-loc: d3dumddi.h
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
req.typenames: DXGK_PTE
---

# PFND3DDDI_CRYPTOSESSIONKEYEXCHANGE callback



## -description
The <b>CryptoSessionKeyExchange</b> function negotiates a session key. 



## -prototype

````
PFND3DDDI_CRYPTOSESSIONKEYEXCHANGE CryptoSessionKeyExchange;

__checkReturn HRESULT APIENTRY CryptoSessionKeyExchange(
  _In_    HANDLE                             hDevice,
  _Inout_ D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_cryptosessionkeyexchange.md">D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE</a> structure that describes a session key that is used for encryption. 


## -returns
<b>CryptoSessionKeyExchange</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The session key is successfully exchanged. 
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_cryptosessionkeyexchange.md">CryptoSessionKeyExchange</a> could not allocate the required memory for it to complete.

 


## -remarks
The driver should only support a single key exchange mechanism for each encryption type. Microsoft has standardized the key exchange type D3DKEYEXCHANGE_RSAES_OAEP. However, hardware vendors can use proprietary key exchange mechanisms. 

For D3DKEYEXCHANGE_RSAES_OAEP, the <b>pData</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_cryptosessionkeyexchange.md">D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE</a> structure points to a buffer that contains the session key that an application previously RSAES-OAEP-encrypted with the public key from the driver's crypto session certificate. The actual size of the buffer is 256 bytes. This exchange is identical to how the <a href="https://msdn.microsoft.com/2c138dbd-55ca-4c71-8c8b-b2efd1ca80f2">Output Protection Manager</a> (OPM) key exchange works, except the OPM buffer contains additional data besides the session key. The same certificate that is used for OPM key exchange can be used for the D3DKEYEXCHANGE_RSAES_OAEP key exchange. 


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_cryptosessionkeyexchange.md">D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_CRYPTOSESSIONKEYEXCHANGE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

