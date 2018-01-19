---
UID: NC:d3d10umddi.PFND3D10DDI_SETCONSTANTBUFFERS
title: PFND3D10DDI_SETCONSTANTBUFFERS
author: windows-driver-content
description: The CsSetConstantBuffers function sets constant buffers for a compute shader.
old-location: display\cssetconstantbuffers.htm
old-project: display
ms.assetid: 159ee0ac-7ddf-4ffd-a07f-3d58130b90e8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CsSetConstantBuffers is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CsSetConstantBuffers
req.alt-loc: d3d10umddi.h
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

# PFND3D10DDI_SETCONSTANTBUFFERS callback



## -description
The <b>CsSetConstantBuffers</b> function sets constant buffers for a compute shader. 



## -prototype

````
PFND3D10DDI_SETCONSTANTBUFFERS CsSetConstantBuffers;

VOID APIENTRY CsSetConstantBuffers(
  _In_       D3D10DDI_HDEVICE   hDevice,
  _In_       UINT               StartBuffer,
  _In_       UINT               NumBuffers,
  _In_ const D3D10DDI_HRESOURCE *phBuffers
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param StartBuffer [in]

 The starting constant buffer to set. 


### -param NumBuffers [in]

 The total number of buffers to set. 


### -param phBuffers [in]

 An array of handles to the constant buffers, beginning with the buffer that <b>StartBuffer</b> specifies.


## -returns
None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.


## -remarks
Buffers that the <b>CsSetConstantBuffers</b> function specifies are created with the D3D10_BIND_CONSTANT_BUFFER flag. 

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Direct3D runtime determines that the error is critical. Even if the device is removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interferes with the operation of <b>CsSetConstantBuffers</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_SETCONSTANTBUFFERS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

