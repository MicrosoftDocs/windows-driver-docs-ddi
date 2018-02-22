---
UID: NS:d3dkmddi._DXGK_HISTORY_BUFFER_HEADER
title: "_DXGK_HISTORY_BUFFER_HEADER"
author: windows-driver-content
description: Specifies how data is stored in a DXGK_HISTORY_BUFFER history buffer.
old-location: display\dxgk_history_buffer_header.htm
old-project: display
ms.assetid: 246EBAFC-EBEB-4B58-83C1-731314CECF2E
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgk_history_buffer_header, DXGK_HISTORY_BUFFER_HEADER structure [Display Devices], d3dkmddi/DXGK_HISTORY_BUFFER_HEADER, DXGK_HISTORY_BUFFER_HEADER, _DXGK_HISTORY_BUFFER_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dkmddi.h
apiname:
-	DXGK_HISTORY_BUFFER_HEADER
product: Windows
targetos: Windows
req.typenames: DXGK_HISTORY_BUFFER_HEADER
---

# _DXGK_HISTORY_BUFFER_HEADER structure


## -description


Specifies how data is stored in a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_history_buffer.md">DXGK_HISTORY_BUFFER</a> history buffer.


## -syntax


````
typedef struct _DXGK_HISTORY_BUFFER_HEADER {
  UINT32 RenderCbSequence;
  UINT32 NumTimestamps;
  UINT32 PrivateDataSize;
  UINT32 Reserved;
} DXGK_HISTORY_BUFFER_HEADER;
````


## -struct-fields




### -field RenderCbSequence

The value of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_renderflags.md">D3DDDICB_RENDERFLAGS</a>.<b>Value</b> member that is to be used in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a> function.

The display miniport driver should compute this value and enter it into <b>DXGK_HISTORY_BUFFER_HEADER</b> before calling <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a>.


### -field NumTimestamps

The number of time stamps that will be in the history buffer when the DMA buffer completes its execution.

The driver should include all time stamps that are logged, even if the buffer must be formatted before being logged to the Event Tracing for Windows (ETW) facility.


### -field PrivateDataSize

The size, in bytes, of optional private data that the driver stores. The driver can use this data for any purpose.

If zero, the driver doesn't need to store private data in the history buffer.

<div class="alert"><b>Note</b>  This value should be a multiple of 8 bytes to ensure that time stamp data is aligned to a 64-bit boundary.</div>
<div> </div>
If the history buffer doesn't need to be formatted when the DMA buffer completes its execution, then when the DirectX graphics kernel subsystem writes logs to ETW, it uses <b>PrivateDataSize</b> as a direct offset from the header to reference the time stamps.


### -field Reserved

Reserved for system use and must be set to zero.


## -remarks



Only the time stamp portion of the history buffer, along with  the number of time stamps, will be logged to ETW. Header data and private driver data will not be logged to ETW as part of the time stamp buffer. However, parts of the header will be logged separately.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_renderflags.md">D3DDDICB_RENDERFLAGS</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_history_buffer.md">DXGK_HISTORY_BUFFER</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_HISTORY_BUFFER_HEADER structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

