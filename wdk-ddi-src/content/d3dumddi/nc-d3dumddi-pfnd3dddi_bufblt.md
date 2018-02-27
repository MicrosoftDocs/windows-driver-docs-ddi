---
UID: NC:d3dumddi.PFND3DDDI_BUFBLT
title: PFND3DDDI_BUFBLT
author: windows-driver-content
description: The BufBlt function performs a bit-block transfer (bitblt) operation from a source vertex or index buffer to a destination vertex or index buffer.
old-location: display\bufblt.htm
old-project: display
ms.assetid: d75f3fad-3bcd-44ad-9bd5-f61f5346cf8d
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: BufBlt, BufBlt callback function [Display Devices], PFND3DDDI_BUFBLT, UserModeDisplayDriver_Functions_87f3469d-cae9-43e7-a0ae-d19bef34314e.xml, d3dumddi/BufBlt, display.bufblt
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	BufBlt
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_BUFBLT callback


## -description


The <b>BufBlt</b> function performs a bit-block transfer (bitblt) operation from a source vertex or index buffer to a destination vertex or index buffer.


## -prototype


````
PFND3DDDI_BUFBLT BufBlt;

__checkReturn HRESULT APIENTRY BufBlt(
  _In_       HANDLE              hDevice,
  _In_ const D3DDDIARG_BUFFERBLT *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_bufferblt.md">D3DDDIARG_BUFFERBLT</a> structure that describes the parameters of the buffer bitblt operation.


## -returns



<b>BufBlt</b> returns S_OK or an appropriate error result if the buffer bitblt operation is not successfully performed.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_bufferblt.md">D3DDDIARG_BUFFERBLT</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_BUFBLT callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

