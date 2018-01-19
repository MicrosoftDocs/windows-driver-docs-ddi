---
UID: NC:d3dumddi.PFND3DDDI_VALIDATEDEVICE
title: PFND3DDDI_VALIDATEDEVICE
author: windows-driver-content
description: The ValidateDevice function returns the number of passes in which the hardware can perform the blending operations that are specified in the current state.
old-location: display\validatedevice.htm
old-project: display
ms.assetid: 058696e0-be4a-45f3-b3e8-55abccdce3ce
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
req.alt-api: ValidateDevice
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

# PFND3DDDI_VALIDATEDEVICE callback



## -description
The <i>ValidateDevice</i> function returns the number of passes in which the hardware can perform the blending operations that are specified in the current state.



## -prototype

````
PFND3DDDI_VALIDATEDEVICE ValidateDevice;

__checkReturn HRESULT APIENTRY ValidateDevice(
  _In_    HANDLE                              hDevice,
  _Inout_ D3DDDIARG_VALIDATETEXTURESTAGESTATE *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_validatetexturestagestate.md">D3DDDIARG_VALIDATETEXTURESTAGESTATE</a> structure that receives the number of passes in which the hardware can perform the blending operations.


## -returns
<i>ValidateDevice</i> returns S_OK or an appropriate error result if the number of necessary hardware passes is not successfully received.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_validatetexturestagestate.md">D3DDDIARG_VALIDATETEXTURESTAGESTATE</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_VALIDATEDEVICE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

