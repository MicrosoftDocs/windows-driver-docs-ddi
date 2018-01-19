---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY
title: PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY
author: windows-driver-content
description: Allows the driver to return independent hardware vendor (IHV)-specific information used when initializing the new hardware key.
old-location: display\getdatafornewhardwarekey.htm
old-project: display
ms.assetid: 0B365C66-2E6E-4DE9-A7A4-963965995F61
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
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
req.alt-api: pfnGetDataForNewHardwareKey
req.alt-loc: D3d10umddi.h
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
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY callback



## -description
Allows the driver to return independent hardware vendor (IHV)-specific information used when initializing the new hardware key.



## -prototype

````
PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY pfnGetDataForNewHardwareKey;

typedef HRESULT APIENTRY* pfnGetDataForNewHardwareKey(
  _In_        D3D10DDI_HDEVICE          hDevice,
  _In_        D3D11_1DDI_HCRYPTOSESSION  hCryptoSession,
  _In_        UINT                      PrivateInputSize,
  _In_  const void                      *pPrivatInputData,
  _Out_       UINT64                    *pPrivateOutputData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param  hCryptoSession [in]

A handle to the cryptographic session object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a> function.


### -param PrivateInputSize [in]

The size of the  buffer pointed to by <b>pPrivatInputData</b>, in bytes.


### -param pPrivatInputData [in]

A pointer to a buffer that receives private input data for the driver.


### -param pPrivateOutputData [out]

A pointer to a UINT64 value that receives private driver output data that could be used later by the secure DRM component when initializing the key.


## -returns

      Returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>Private driver data was successfully returned.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
        Memory was not available to complete the operation.


 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM2_0DDI_GETDATAFORNEWHARDWAREKEY callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

