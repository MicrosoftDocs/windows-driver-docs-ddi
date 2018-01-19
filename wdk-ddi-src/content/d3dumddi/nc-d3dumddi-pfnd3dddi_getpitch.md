---
UID: NC:d3dumddi.PFND3DDDI_GETPITCH
title: PFND3DDDI_GETPITCH
author: windows-driver-content
description: The GetPitch function retrieves the pitch of a protected or non-lockable surface.
old-location: display\getpitch.htm
old-project: display
ms.assetid: 1a5721a3-c03f-4827-9626-c9b6af5059a1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: GetPitch is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GetPitch
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

# PFND3DDDI_GETPITCH callback



## -description
The <i>GetPitch</i> function retrieves the pitch of a protected or non-lockable surface. 



## -prototype

````
PFND3DDDI_GETPITCH GetPitch;

__checkReturn HRESULT APIENTRY GetPitch(
  _In_    HANDLE             hDevice,
  _Inout_ D3DDDIARG_GETPITCH *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context). 


### -param pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getpitch.md">D3DDDIARG_GETPITCH</a> structure that describes the protected surface. 


## -returns
The <i>GetPitch</i> function returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The pitch of the protected surface is successfully retrieved. 
<dl>
<dt><b>D3DDDIERR_NOTAVAILABLE</b></dt>
</dl>The driver does not support the <i>GetPitch</i> function. 

 


## -remarks
Hardware and drivers can optionally support the <i>GetPitch</i> function.  

The surface for which the <i>GetPitch</i> function returns the pitch can be non-lockable or protected. Therefore, the application cannot retrieve the pitch of the surface through a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lock.md">Lock</a> function. The application must retrieve the pitch of the surface to properly allocate the system memory buffer that the application subsequently uses in calls to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_encryptionblt.md">EncryptionBlt</a> and <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decryptionblt.md">DecryptionBlt</a> functions. 


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_getpitch.md">D3DDDIARG_GETPITCH</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decryptionblt.md">DecryptionBlt</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_encryptionblt.md">EncryptionBlt</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_GETPITCH callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

