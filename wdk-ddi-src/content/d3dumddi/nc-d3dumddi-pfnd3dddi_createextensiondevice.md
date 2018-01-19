---
UID: NC:d3dumddi.PFND3DDDI_CREATEEXTENSIONDEVICE
title: PFND3DDDI_CREATEEXTENSIONDEVICE
author: windows-driver-content
description: The CreateExtensionDevice function creates a Microsoft DirectX Video Acceleration (DirectX VA) extension device.
old-location: display\createextensiondevice.htm
old-project: display
ms.assetid: 7e6dbb70-2e74-4ddb-a504-2c8145af99d9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CreateExtensionDevice
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

# PFND3DDDI_CREATEEXTENSIONDEVICE callback



## -description
The <b>CreateExtensionDevice</b> function creates a Microsoft DirectX Video Acceleration (DirectX VA) extension device. 



## -prototype

````
PFND3DDDI_CREATEEXTENSIONDEVICE CreateExtensionDevice;

__checkReturn HRESULT APIENTRY CreateExtensionDevice(
  _In_    HANDLE                          hDevice,
  _Inout_ D3DDDIARG_CREATEEXTENSIONDEVICE *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createextensiondevice.md">D3DDDIARG_CREATEEXTENSIONDEVICE</a> structure. On input, this structure contains information that the driver can use. On output, the driver specifies information in the structure that the Microsoft Direct3D runtime can use.


## -returns
<b>CreateExtensionDevice</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The extension device is successfully created.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createextensiondevice.md">CreateExtensionDevice</a> could not allocate the required memory for it to complete.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createextensiondevice.md">D3DDDIARG_CREATEEXTENSIONDEVICE</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroyextensiondevice.md">DestroyExtensionDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_CREATEEXTENSIONDEVICE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

