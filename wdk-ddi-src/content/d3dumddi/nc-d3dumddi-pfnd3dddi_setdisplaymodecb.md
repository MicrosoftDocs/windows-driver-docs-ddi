---
UID: NC:d3dumddi.PFND3DDDI_SETDISPLAYMODECB
title: PFND3DDDI_SETDISPLAYMODECB
author: windows-driver-content
description: The pfnSetDisplayModeCb function sets the allocation that is used to scan out to the display.
old-location: display\pfnsetdisplaymodecb.htm
old-project: display
ms.assetid: a1f58757-809d-4351-8b1a-fd4420981c24
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
req.alt-api: pfnSetDisplayModeCb
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

# PFND3DDDI_SETDISPLAYMODECB callback



## -description
The <b>pfnSetDisplayModeCb</b> function sets the allocation that is used to scan out to the display.



## -prototype

````
PFND3DDDI_SETDISPLAYMODECB pfnSetDisplayModeCb;

__checkReturn HRESULT APIENTRY CALLBACK pfnSetDisplayModeCb(
  _In_    HANDLE                  hDevice,
  _Inout_ D3DDDICB_SETDISPLAYMODE *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).


### -param pData [in, out]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_setdisplaymode.md">D3DDDICB_SETDISPLAYMODE</a> structure that describes the allocation that is used to scan out.


## -returns
<b>pfnSetDisplayModeCb</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The display mode was successfully set.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
        Parameters were validated and determined to be incorrect.
       
<dl>
<dt><b>D3DDDIERR_INCOMPATIBLEPRIVATEFORMAT</b></dt>
</dl>The user-mode display driver must convert the format of the surface that is associated with the allocation that the <b>hPrimaryAllocation</b> member of <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_setdisplaymode.md">D3DDDICB_SETDISPLAYMODE</a> specifies into the format attribute that the <b>PrivateDriverFormatAttribute</b> member of D3DDDICB_SETDISPLAYMODE specifies. The driver should then call <b>pfnSetDisplayModeCb</b> again. The driver could allocate a new allocation, perform a conversion bit-block transfer (bitblt) from the old primary surface to the new, and then destroy the old primary as long as the driver uses the new allocation handle for this allocation for all subsequent operations. The driver should repeat this process until <b>pfnSetDisplayModeCb</b> returns a different return value. 

 

This function might also return other HRESULT values.




## -remarks
After the Microsoft Direct3D runtime calls the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplaymode.md">SetDisplayMode</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff569536">SetDisplayModeDXGI</a> function to set the primary surface to be scanned out to the display, the user-mode display driver calls the <b>pfnSetDisplayModeCb</b> function to set the underlying primary allocation that is used for scanning out. 


<b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnSetDisplayModeCb</b>, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.



<b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnSetDisplayModeCb</b>, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.

The following code example shows how to set the allocation for scanning out to the display.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_setdisplaymode.md">D3DDDICB_SETDISPLAYMODE</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplaymode.md">SetDisplayMode</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569536">SetDisplayModeDXGI</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETDISPLAYMODECB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

