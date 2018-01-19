---
UID: NC:d3dumddi.PFND3DDDI_STARTSESSIONKEYREFRESH
title: PFND3DDDI_STARTSESSIONKEYREFRESH
author: windows-driver-content
description: The StartSessionKeyRefresh function returns a random number that the driver's FinishSessionKeyRefresh function subsequently uses to perform an exclusive OR operation (XOR) with the session key.
old-location: display\startsessionkeyrefresh.htm
old-project: display
ms.assetid: 986d8f46-3b4f-41b2-938e-4f3adbfe057a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: StartSessionKeyRefresh is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StartSessionKeyRefresh
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

# PFND3DDDI_STARTSESSIONKEYREFRESH callback



## -description
The <i>StartSessionKeyRefresh</i> function returns a random number that the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_finishsessionkeyrefresh.md">FinishSessionKeyRefresh</a> function subsequently uses to perform an exclusive OR operation (XOR) with the session key. 



## -prototype

````
PFND3DDDI_STARTSESSIONKEYREFRESH StartSessionKeyRefresh;

__checkReturn HRESULT APIENTRY StartSessionKeyRefresh(
  _In_          HANDLE                           hDevice,
  _Inout_ const D3DDDIARG_STARTSESSIONKEYREFRESH *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_startsessionkeyrefresh.md">D3DDDIARG_STARTSESSIONKEYREFRESH</a> structure that contains information about the random number. 


## -returns
<i>StartSessionKeyRefresh</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The random number is successfully returned. 
<dl>
<dt><b>D3DDDIERR_NOTAVAILABLE</b></dt>
</dl>The driver does not support the <i>StartSessionKeyRefresh</i> function. 

 


## -remarks
The hardware and driver can optionally support <i>StartSessionKeyRefresh</i> for all crypto types.  

When the Direct3D runtime calls the driver's <i>StartSessionKeyRefresh</i> function, the driver generates and saves a random number and returns the random number in the buffer that the <b>pRandomNumber</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_startsessionkeyrefresh.md">D3DDDIARG_STARTSESSIONKEYREFRESH</a> structure points to.

When the runtime subsequently calls the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_finishsessionkeyrefresh.md">FinishSessionKeyRefresh</a> function, the driver performs an XOR operation of the random number with the session key.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_startsessionkeyrefresh.md">D3DDDIARG_STARTSESSIONKEYREFRESH</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_finishsessionkeyrefresh.md">FinishSessionKeyRefresh</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_STARTSESSIONKEYREFRESH callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

