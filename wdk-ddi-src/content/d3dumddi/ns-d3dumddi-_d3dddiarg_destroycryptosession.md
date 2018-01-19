---
UID: NS:d3dumddi._D3DDDIARG_DESTROYCRYPTOSESSION
title: _D3DDDIARG_DESTROYCRYPTOSESSION
author: windows-driver-content
description: The D3DDDIARG_DESTROYCRYPTOSESSION structure contains the handle to an encryption session that is destroyed in a call to the DestroyCryptoSession function.
old-location: display\d3dddiarg_destroycryptosession.htm
old-project: display
ms.assetid: 7ae8bfd7-da94-41b0-8995-34194b2ad8a7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDIARG_DESTROYCRYPTOSESSION, D3DDDIARG_DESTROYCRYPTOSESSION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DESTROYCRYPTOSESSION is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_DESTROYCRYPTOSESSION
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
req.typenames: D3DDDIARG_DESTROYCRYPTOSESSION
---

# _D3DDDIARG_DESTROYCRYPTOSESSION structure



## -description
The D3DDDIARG_DESTROYCRYPTOSESSION structure contains the handle to an encryption session that is destroyed in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroycryptosession.md">DestroyCryptoSession</a> function. 



## -syntax

````
typedef struct _D3DDDIARG_DESTROYCRYPTOSESSION {
  HANDLE hCryptoSession;
} D3DDDIARG_DESTROYCRYPTOSESSION;
````


## -struct-fields

### -field hCryptoSession

[in] The handle to the encryption session that the driver destroys.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_destroycryptosession.md">DestroyCryptoSession</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DESTROYCRYPTOSESSION structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

