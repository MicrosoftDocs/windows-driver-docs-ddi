---
UID: NS:d3dumddi._D3DDDIARG_WINFO
title: _D3DDDIARG_WINFO
author: windows-driver-content
description: The D3DDDIARG_WINFO structure describes a w range for w buffering.
old-location: display\d3dddiarg_winfo.htm
old-project: display
ms.assetid: 82ab59d7-302a-4e3a-b5e6-6a332eafcbed
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDIARG_WINFO, D3DDDIARG_WINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_WINFO
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
req.typenames: D3DDDIARG_WINFO
---

# _D3DDDIARG_WINFO structure



## -description
The D3DDDIARG_WINFO structure describes a w range for w buffering. 



## -syntax

````
typedef struct _D3DDDIARG_WINFO {
  FLOAT WNear;
  FLOAT WFar;
} D3DDDIARG_WINFO;
````


## -struct-fields

### -field WNear

[in] A FLOAT value that indicates the near limit in the w range. 


### -field WFar

[in] A FLOAT value that indicates the far limit in the w range. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updatewinfo.md">UpdateWInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_WINFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

