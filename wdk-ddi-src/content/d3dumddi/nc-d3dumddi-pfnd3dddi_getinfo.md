---
UID: NC:d3dumddi.PFND3DDDI_GETINFO
title: PFND3DDDI_GETINFO
author: windows-driver-content
description: The GetInfo function retrieves information about the specified display device.
old-location: display\getinfo.htm
old-project: display
ms.assetid: dcc0519e-f919-48bc-829f-416648de0b40
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
req.alt-api: GetInfo
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

# PFND3DDDI_GETINFO callback



## -description
The <i>GetInfo</i> function retrieves information about the specified display device.



## -prototype

````
PFND3DDDI_GETINFO GetInfo;

__checkReturn HRESULT APIENTRY GetInfo(
   __in HANDLE                   hDevice,
   __in UINT                     DevInfoID,
   __out_bcount(DevInfoSize)VOID *pDevInfoStruct,
   __in UINT                     DevInfoSize
)
{ ... }
````


## -parameters

### -param hDevice 

 A handle to the display device (graphics context).


### -param DevInfoID 

 An identifier for the type of device information to retrieve.


### -param pDevInfoStruct 

 A pointer to a buffer of the type that <i>DevInfoID</i> specifies that receives information about the device.


### -param DevInfoSize 

 The size, in bytes, of the buffer that is supplied by <i>pDevInfoStruct</i>.


## -returns
<i>GetInfo</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The device information is successfully retrieved.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The driver does not support the requested type of device information.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 


## -remarks
The Microsoft DirectX 7 and DirectX 8 runtimes call the <i>GetInfo</i> function to query a user-mode display driver for additional device information.

The Direct3D 8 runtime sets the D3DDDIDEVINFOID_VCACHE flag in the <i>DevInfoID</i> parameter and specifies an empty <a href="..\d3dumddi\ns-d3dumddi-_d3dddidevinfo_vcache.md">D3DDDIDEVINFO_VCACHE</a> structure in the <i>pDevInfoStruct</i> parameter to query the user-mode display driver's support for vertex cache.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddidevinfo_vcache.md">D3DDDIDEVINFO_VCACHE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_GETINFO callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

