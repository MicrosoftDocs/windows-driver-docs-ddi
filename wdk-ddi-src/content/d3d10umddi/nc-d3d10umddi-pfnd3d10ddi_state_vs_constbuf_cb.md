---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_VS_CONSTBUF_CB
title: PFND3D10DDI_STATE_VS_CONSTBUF_CB
author: windows-driver-content
description: The pfnStateVsConstBufCb function causes the Microsoft Direct3D 10 runtime to refresh the vertex shader stage's bound constant buffers.
old-location: display\pfnstatevsconstbufcb.htm
old-project: display
ms.assetid: 43aa7188-d6aa-4890-8eac-1342a984005b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnStateVsConstBufCb
req.alt-loc: d3d10umddi.h
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
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D10DDI_STATE_VS_CONSTBUF_CB callback



## -description
The <b>pfnStateVsConstBufCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the vertex shader stage's bound constant buffers.



## -prototype

````
PFND3D10DDI_STATE_VS_CONSTBUF_CB pfnStateVsConstBufCb;

void APIENTRY pfnStateVsConstBufCb(
  _In_ D3D10DDI_HRTCORELAYER hRuntimeDevice,
  _In_ UINT                  Base,
  _In_ UINT                  Count
)
{ ... }
````


## -parameters

### -param hRuntimeDevice [in]

 A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function. 


### -param Base [in]

 The starting constant buffer to refresh. 


### -param Count [in]

 The total number of buffers to refresh. The number can be -1, which specifies that the Direct3D runtime will use its high watermarks to substitute an optimal value (which is typically less than the maximum valid value for <i>Count</i>). However, no non-NULL binding exists in a slot larger than the optimal <i>Count</i> value.


## -returns
None


## -remarks
The <i>Base</i> and <i>Count</i> parameters that the driver passes to the <b>pfnStateVsConstBufCb</b> function directly correspond to the <i>StartBuffer</i> and <i>NumBuffers</i> parameters that are passed to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md">VsSetConstantBuffers</a> function.


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks.md">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md">VsSetConstantBuffers</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_STATE_VS_CONSTBUF_CB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

