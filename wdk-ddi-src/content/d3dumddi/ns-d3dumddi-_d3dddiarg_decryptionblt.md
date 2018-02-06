---
UID: NS:d3dumddi._D3DDDIARG_DECRYPTIONBLT
title: "_D3DDDIARG_DECRYPTIONBLT"
author: windows-driver-content
description: The D3DDDIARG_DECRYPTIONBLT structure describes the parameters of an decrypted bit-block transfer (bitblt) in a call to the DecryptionBlt function.
old-location: display\d3dddiarg_decryptionblt.htm
old-project: display
ms.assetid: cc11e153-6be6-4fbc-9535-98bab7ed2b90
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dddiarg_decryptionblt, d3dumddi/D3DDDIARG_DECRYPTIONBLT, _D3DDDIARG_DECRYPTIONBLT, UMDisplayDriver_param_Structs_1d0c0adb-cfde-47fd-b17c-1acc15de25cd.xml, D3DDDIARG_DECRYPTIONBLT, D3DDDIARG_DECRYPTIONBLT structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DECRYPTIONBLT is supported beginning with the Windows 7 operating system.
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
-	D3DDDIARG_DECRYPTIONBLT
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_DECRYPTIONBLT
---

# _D3DDDIARG_DECRYPTIONBLT structure


## -description


The D3DDDIARG_DECRYPTIONBLT structure describes the parameters of an decrypted bit-block transfer (bitblt) in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decryptionblt.md">DecryptionBlt</a> function. 


## -syntax


````
typedef struct _D3DDDIARG_DECRYPTIONBLT {
  HANDLE                     hCryptoSession;
  HANDLE                     hSrcResource;
  UINT                       SrcSubResourceIndex;
  HANDLE                     hDstResource;
  UINT                       DstSubResourceIndex;
  UINT                       SrcResourceSize;
  D3DDDIENCRYPTED_BLOCK_INFO *pEncryptedBlockInfo;
  VOID                       *pContentKey;
  VOID                       *pIV;
} D3DDDIARG_DECRYPTIONBLT;
````


## -struct-fields




### -field hCryptoSession

[in] A handle to the encryption session. 


### -field hSrcResource

[in] A handle to the source resource.


### -field SrcSubResourceIndex

[in] The index to the source surface within the resource. 


### -field hDstResource

[in] A handle to the destination resource. 


### -field DstSubResourceIndex

[in] The index to the destination surface within the resource. 


### -field SrcResourceSize

[in] The size, in bytes, of the source resource. 


### -field pEncryptedBlockInfo

[in] A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiencrypted_block_info.md">D3DDDIENCRYPTED_BLOCK_INFO</a> structure that describes the portions of the buffer that are encrypted. 


### -field pContentKey

[in] A pointer to a block of memory that contains the content key that is required to decrypt the bitblt data. If <b>pContentKey</b> is <b>NULL</b>, hardware does not require a separate content key to decrypt the data. That is, the session key is used to encrypt the data. 


### -field pIV

[in] A pointer to a block of memory that contains the initialization vector that is required to decrypt the bitblt data. If <b>pIV</b> is <b>NULL</b>, hardware does not require a separate initialization vector to decrypt the data. That is, the session key is used to encrypt the data. 


## -remarks


A pointer to a populated D3DDDIARG_DECRYPTIONBLT structure is passed to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decryptionblt.md">DecryptionBlt</a> function to write data to a protected surface. 



## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiencrypted_block_info.md">D3DDDIENCRYPTED_BLOCK_INFO</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decryptionblt.md">DecryptionBlt</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DECRYPTIONBLT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

