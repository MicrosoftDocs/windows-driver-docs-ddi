---
UID: NC:d3dumddi.PFND3DDDI_DECODEENDFRAME
title: PFND3DDDI_DECODEENDFRAME
author: windows-driver-content
description: The DecodeEndFrame function notifies the user-mode display driver that all of the data that was required to decode the current frame was submitted.
old-location: display\decodeendframe.htm
old-project: display
ms.assetid: 6e8d3280-6ddc-4593-9208-c4f0c9ff254c
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
req.alt-api: DecodeEndFrame
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

# PFND3DDDI_DECODEENDFRAME callback



## -description
The <b>DecodeEndFrame</b> function notifies the user-mode display driver that all of the data that was required to decode the current frame was submitted.



## -prototype

````
PFND3DDDI_DECODEENDFRAME DecodeEndFrame;

__checkReturn HRESULT APIENTRY DecodeEndFrame(
  _In_    HANDLE                   hDevice,
  _Inout_ D3DDDIARG_DECODEENDFRAME *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decodeendframe.md">D3DDDIARG_DECODEENDFRAME</a> structure that describes the DirectX VA decoder that should stop decoding a frame.


## -returns
<b>DecodeEndFrame</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>Decoding successfully completed.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>DecodeEndFrame could not allocate the required memory for it to complete.

 


## -remarks
The <b>DecodeEndFrame</b> function notifies the user-mode display driver that its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeexecute.md">DecodeExecute</a> function can no longer be called on the specified decode device.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decodeendframe.md">D3DDDIARG_DECODEENDFRAME</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeexecute.md">DecodeExecute</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DECODEENDFRAME callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

