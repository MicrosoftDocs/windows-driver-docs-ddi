---
UID: NS:d3dumddi._D3DDDIENCRYPTED_BLOCK_INFO
title: "_D3DDDIENCRYPTED_BLOCK_INFO" (d3dumddi.h)
description: The D3DDDIENCRYPTED_BLOCK_INFO structure describes the portions of a buffer that are encrypted.
old-location: display\d3dddiencrypted_block_info.htm
tech.root: display
ms.assetid: a02f782f-6918-479a-b3de-9443df2e9ffe
ms.date: 05/10/2018
ms.keywords: D3DDDIENCRYPTED_BLOCK_INFO, D3DDDIENCRYPTED_BLOCK_INFO structure [Display Devices], D3D_other_Structs_ca22516f-415c-47ff-9ba5-b837171cf77e.xml, _D3DDDIENCRYPTED_BLOCK_INFO, d3dumddi/D3DDDIENCRYPTED_BLOCK_INFO, display.d3dddiencrypted_block_info
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIENCRYPTED_BLOCK_INFO is supported beginning with the Windows 7 operating system.
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
-	D3DDDIENCRYPTED_BLOCK_INFO
product:
- Windows
targetos: Windows
req.typenames: D3DDDIENCRYPTED_BLOCK_INFO
---

# _D3DDDIENCRYPTED_BLOCK_INFO structure


## -description


The D3DDDIENCRYPTED_BLOCK_INFO structure describes the portions of a buffer that are encrypted. 


## -struct-fields




### -field NumEncryptedBytesAtBeginning

[in] The number of bytes at the beginning of the buffer that are encrypted. 


### -field NumBytesInSkipPattern

[in] The number of bytes in the buffer that are skipped from encryption before encryption starts again. 


### -field NumBytesInEncryptPattern

[in] The number of bytes in the buffer that are encrypted after the skip pattern, which the <b>NumBytesInSkipPattern</b> member specifies. The skip and encrypt pattern is then repeated until the buffer ends. For more information about the skip-encrypt pattern, see the Remarks section. 


## -remarks



Because the buffer's encrypted portion is specified in bytes, an application must ensure that the encrypted blocks match the GPU's crypto-block alignment. 

The runtime can specify a populated D3DDDIENCRYPTED_BLOCK_INFO structure in the block of memory that the <b>pEncryptedBlockInfo</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543011">D3DDDIARG_DECRYPTIONBLT</a> structure points to when the runtime calls the driver's <a href="https://msdn.microsoft.com/1bfe2b9c-90f6-48bf-b0b3-30788ef94110">DecryptionBlt</a> function to write data to a protected surface. 

The following examples show how the runtime can partition a buffer's encryption.

<ol>
<li>The following values encrypt the first 100 bytes of the buffer and skip the remaining buffer data:<ul>
<li><b>NumEncryptedBytesAtBeginning</b> = 100;</li>
<li><b>NumBytesInSkipPattern</b> = 0;</li>
<li><b>NumBytesInEnycryptPattern</b> = 0;</li>
</ul>
</li>
<li>The following values encrypt the first 100 bytes of the buffer, skips the next 20 bytes, and then encrypt the next 2 bytes blocks. The process is then repeated where these values skip 20 bytes and encrypt 2 bytes until the end of the buffer.<ul>
<li><b>NumEncryptedBytesAtBeginning</b> = 100;</li>
<li><b>NumBytesInSkipPattern</b> = 20;</li>
<li><b>NumBytesInEnycryptPattern</b> = 2;</li>
</ul>
</li>
</ol>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543011">D3DDDIARG_DECRYPTIONBLT</a>



<a href="https://msdn.microsoft.com/1bfe2b9c-90f6-48bf-b0b3-30788ef94110">DecryptionBlt</a>
 

 

