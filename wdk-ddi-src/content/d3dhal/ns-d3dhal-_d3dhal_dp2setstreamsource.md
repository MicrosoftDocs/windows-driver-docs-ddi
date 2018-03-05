---
UID: NS:d3dhal._D3DHAL_DP2SETSTREAMSOURCE
title: "_D3DHAL_DP2SETSTREAMSOURCE"
author: windows-driver-content
description: DirectX 8.0 and later versions only. The D3DHAL_DP2SETSTREAMSOURCE structure is used to bind a vertex stream source to a vertex buffer for D3dDrawPrimitives2.
old-location: display\d3dhal_dp2setstreamsource.htm
old-project: display
ms.assetid: 23be14ce-2312-41e0-98c5-07de551ffce9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPD3DHAL_DP2SETSTREAMSOURCE, D3DHAL_DP2SETSTREAMSOURCE, D3DHAL_DP2SETSTREAMSOURCE structure [Display Devices], LPD3DHAL_DP2SETSTREAMSOURCE, LPD3DHAL_DP2SETSTREAMSOURCE structure pointer [Display Devices], _D3DHAL_DP2SETSTREAMSOURCE, d3dhal/D3DHAL_DP2SETSTREAMSOURCE, d3dhal/LPD3DHAL_DP2SETSTREAMSOURCE, d3dstrct_4a6ddce7-b2fc-4fdd-bbed-cc905b1bc97d.xml, display.d3dhal_dp2setstreamsource"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	HeaderDef
api_location:
-	d3dhal.h
api_name:
-	D3DHAL_DP2SETSTREAMSOURCE
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2SETSTREAMSOURCE
---

# _D3DHAL_DP2SETSTREAMSOURCE structure


## -description



   DirectX 8.0 and later versions only.
   

The D3DHAL_DP2SETSTREAMSOURCE structure is used to bind a vertex stream source to a vertex buffer for <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.


## -syntax


````
typedef struct _D3DHAL_DP2SETSTREAMSOURCE {
  DWORD dwStream;
  DWORD dwVBHandle;
  DWORD dwStride;
} D3DHAL_DP2SETSTREAMSOURCE, *LPD3DHAL_DP2SETSTREAMSOURCE;
````


## -struct-fields




### -field dwStream

Specifies the stream being bound. It has a value between zero and the maximum number of streams specified by the driver.


### -field dwVBHandle

Specifies the vertex buffer handle. It is legal for the vertex buffer handle to be zero, in which case the stream is no longer bound to a vertex buffer.


### -field dwStride

Specifies the vertex size in bytes.


## -remarks



A driver is notified of the binding of a vertex buffer to a particular stream through a new DP2 token, D3DDP2OP_SETSTREAMSOURCE.

The debug runtime validates that <b>dwStream</b> is within the legal range but the retail version does not, so validation must be present in the driver. DirectX 8.0 does not define the behavior of the driver or hardware in the error case where the stream index given is larger than the maximum stream supported by the hardware (as reported through <b>MaxStreams</b> in D3DCAPS8) beyond requiring that the driver and hardware combination not fault or hang in this case and that, on restoration of correct state the driver and hardware combination should continue to operate normally. Debug versions of your display driver should display messages in the debug output stream indicating when this problem has been detected.

The runtime does not validate that the streams accessed by the current vertex shader are non-NULL. It is the responsibility of the driver writer to ensure the driver/hardware does not crash when this error case arises. Debug versions of your display driver should display messages in the debug output stream to indicate when this problem has been detected.

Only a single stream source is set by a <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure. That is, the <b>wStateCount</b> field of the D3DHAL_DP2COMMAND is always one when <b>bCommand</b> is D3DDP2OP_SETSTREAMSOURCE.




## -see-also

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



D3DDP2OP_SETSTREAMSOURCE



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2setstreamsourceum.md">D3DHAL_DP2SETSTREAMSOURCEUM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2SETSTREAMSOURCE structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

