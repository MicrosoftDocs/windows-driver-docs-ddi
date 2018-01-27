---
UID: NC:d3dumddi.PFND3DDDI_DESTROYCRYPTOSESSION
title: PFND3DDDI_DESTROYCRYPTOSESSION
author: windows-driver-content
description: The DestroyCryptoSession function releases resources for the encryption session that the CreateCryptoSession function creates.
old-location: display\destroycryptosession.htm
old-project: display
ms.assetid: 4035ef73-e1a2-49e4-808d-c40c980393a4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.destroycryptosession, DestroyCryptoSession callback function [Display Devices], DestroyCryptoSession, PFND3DDDI_DESTROYCRYPTOSESSION, PFND3DDDI_DESTROYCRYPTOSESSION, d3dumddi/DestroyCryptoSession, UserModeDisplayDriver_Functions_c1fa988d-a8b7-4538-94cd-d364873f4216.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: DestroyCryptoSession is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	d3dumddi.h
apiname: 
-	DestroyCryptoSession
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DESTROYCRYPTOSESSION callback


## -description


The <b>DestroyCryptoSession</b> function releases resources for the encryption session that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a> function creates. 


## -prototype


````
PFND3DDDI_DESTROYCRYPTOSESSION DestroyCryptoSession;

__checkReturn HRESULT APIENTRY DestroyCryptoSession(
  _In_       HANDLE                         hDevice,
  _In_ const D3DDDIARG_DESTROYCRYPTOSESSION *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *






#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_destroycryptosession.md">D3DDDIARG_DESTROYCRYPTOSESSION</a> structure that contains one member that specifies the handle to the encryption session to destroy. 


## -returns


<b>DestroyCryptoSession</b> returns one of the following values:
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
The encryption session is successfully destroyed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroycryptosession.md">DestroyCryptoSession</a> could not allocate the required memory for it to complete.

</td>
</tr>
</table> 



## -see-also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_destroycryptosession.md">D3DDDIARG_DESTROYCRYPTOSESSION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DESTROYCRYPTOSESSION callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

