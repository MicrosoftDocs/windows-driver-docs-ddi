---
UID: NS:d3dkmthk._D3DKMT_GETPRESENTHISTORY
title: "_D3DKMT_GETPRESENTHISTORY"
author: windows-driver-content
description: The D3DKMT_GETPRESENTHISTORY structure describes the state of copying history.
old-location: display\d3dkmt_getpresenthistory.htm
old-project: display
ms.assetid: 6d9b0473-544f-43aa-9358-ec51d84d45d9
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMT_GETPRESENTHISTORY, D3DKMT_GETPRESENTHISTORY structure [Display Devices], OpenGL_Structs_966946a8-3611-4c25-a57f-1fc99c2004d0.xml, _D3DKMT_GETPRESENTHISTORY, d3dkmthk/D3DKMT_GETPRESENTHISTORY, display.d3dkmt_getpresenthistory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dkmthk.h
api_name:
-	D3DKMT_GETPRESENTHISTORY
product: Windows
targetos: Windows
req.typenames: D3DKMT_GETPRESENTHISTORY
---

# _D3DKMT_GETPRESENTHISTORY structure


## -description


The D3DKMT_GETPRESENTHISTORY structure describes the state of copying history.


## -struct-fields




### -field hAdapter

[in] The handle to the graphics adapter. 


### -field ProvidedSize

Supported in Windows 7 and later versions.

[in] The size, in bytes, of the provided buffer that the <b>pTokens</b> member points to. 


### -field WrittenSize

Supported in Windows 7 and later versions.

[out] The size, in bytes, that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546987">D3DKMTGetPresentHistory</a> function copies to the buffer that the <b>pTokens</b> member points to or the required size for first token. 


### -field pTokens

Supported in Windows 7 and later versions.

[in/out] A pointer to the buffer that receives the tokens. Each token is described by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548188">D3DKMT_PRESENTHISTORYTOKEN</a> structure. 


### -field NumTokens

Supported in Windows 7 and later versions.

[out] The number of tokens that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546987">D3DKMTGetPresentHistory</a> function copies to the buffer that the <b>pTokens</b> member points to. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546987">D3DKMTGetPresentHistory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548188">D3DKMT_PRESENTHISTORYTOKEN</a>
 

 

