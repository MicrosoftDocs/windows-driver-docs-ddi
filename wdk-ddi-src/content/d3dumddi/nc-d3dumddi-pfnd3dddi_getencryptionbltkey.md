---
UID: NC:d3dumddi.PFND3DDDI_GETENCRYPTIONBLTKEY
title: PFND3DDDI_GETENCRYPTIONBLTKEY
author: windows-driver-content
description: The GetEncryptionBltKey function returns the key that is used to decrypt the data that the driver's EncryptionBlt function returns.
old-location: display\getencryptionbltkey.htm
old-project: display
ms.assetid: b3c3e792-bc8a-485e-a208-66b7d921cc15
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: GetEncryptionBltKey, GetEncryptionBltKey callback function [Display Devices], PFND3DDDI_GETENCRYPTIONBLTKEY, UserModeDisplayDriver_Functions_c20ad527-141e-404f-a52e-47b893b2a2bb.xml, d3dumddi/GetEncryptionBltKey, display.getencryptionbltkey
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: GetEncryptionBltKey is supported beginning with the Windows 7 operating system.
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
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	GetEncryptionBltKey
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_GETENCRYPTIONBLTKEY callback


## -description


The <i>GetEncryptionBltKey</i> function returns the key that is used to decrypt the data that the driver's <a href="https://msdn.microsoft.com/a92bfff7-8af6-48c3-9e7f-95b9426aaaf2">EncryptionBlt</a> function returns. 


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in, out]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543164">D3DDDIARG_GETENCRYPTIONBLTKEY</a> structure that describes the key for an encrypted session. 


## -returns



<i>GetEncryptionBltKey</i> returns one of the following values:

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
The key for an encrypted session is successfully retrieved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_NOTAVAILABLE</b></dt>
</dl>
</td>
<td width="60%">
The driver does not support the <i>GetEncryptionBltKey</i> function. 

</td>
</tr>
</table>
 




## -remarks



The hardware and driver can optionally support the <i>GetEncryptionBltKey</i> function for all crypto types.  

Each time the Direct3D runtime calls the driver's <i>GetEncryptionBltKey</i> function, the driver should generate a new read-back key. If the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a> function previously created the encryption session with the <b>CryptoType</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542923">D3DDDIARG_CREATECRYPTOSESSION</a> structure set to D3DCRYPTOTYPE_AES128_CTR, the driver and hardware should encrypt the read-back key with the session key.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542923">D3DDDIARG_CREATECRYPTOSESSION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543164">D3DDDIARG_GETENCRYPTIONBLTKEY</a>



<a href="https://msdn.microsoft.com/a92bfff7-8af6-48c3-9e7f-95b9426aaaf2">EncryptionBlt</a>
 

 

