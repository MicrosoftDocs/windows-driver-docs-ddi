---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY
title: PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY
author: windows-driver-content
description: Allows the driver to return independent hardware vendor (IHV)-specific information used when initializing the new hardware key.
old-location: display\getdatafornewhardwarekey.htm
tech.root: display
ms.assetid: 0B365C66-2E6E-4DE9-A7A4-963965995F61
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY, PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY callback, d3d10umddi/pfnGetDataForNewHardwareKey, display.getdatafornewhardwarekey, pfnGetDataForNewHardwareKey, pfnGetDataForNewHardwareKey callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	pfnGetDataForNewHardwareKey
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY callback function


## -description


Allows the driver to return independent hardware vendor (IHV)-specific information used when initializing the new hardware key.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param hCryptoSession [in]

A handle to the cryptographic session object that was created through a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a> function.


### -param PrivateInputSize [in]

The size of the  buffer pointed to by <b>pPrivatInputData</b>, in bytes.


### -param *pPrivatInputData [in]

A pointer to a buffer that receives private input data for the driver.


### -param *pPrivateOutputData [out]

A pointer to a UINT64 value that receives private driver output data that could be used later by the secure DRM component when initializing the key.


## -returns




      Returns one of the following values:

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
Private driver data was successfully returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        Memory was not available to complete the operation.


</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a>
 

 

