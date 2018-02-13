---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_PS_CONSTBUF_CB
title: PFND3D10DDI_STATE_PS_CONSTBUF_CB
author: windows-driver-content
description: The pfnStatePsConstBufCb function causes the Microsoft Direct3D 10 runtime to refresh the pixel shader stage's bound constant buffers.
old-location: display\pfnstatepsconstbufcb.htm
old-project: display
ms.assetid: f4670f69-5154-4f6b-ba98-2b91a16e7b2f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnstatepsconstbufcb, pfnStatePsConstBufCb callback function [Display Devices], pfnStatePsConstBufCb, PFND3D10DDI_STATE_PS_CONSTBUF_CB, PFND3D10DDI_STATE_PS_CONSTBUF_CB, d3d10umddi/pfnStatePsConstBufCb, d3d10state_functions_edcff973-6c62-4cd9-a21f-c40a6afd9548.xml
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
-	d3d10umddi.h
apiname:
-	pfnStatePsConstBufCb
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D10DDI_STATE_PS_CONSTBUF_CB callback


## -description


The <b>pfnStatePsConstBufCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the pixel shader stage's bound constant buffers.


## -prototype


````
PFND3D10DDI_STATE_PS_CONSTBUF_CB pfnStatePsConstBufCb;

void APIENTRY pfnStatePsConstBufCb(
  _In_ D3D10DDI_HRTCORELAYER hRuntimeDevice,
  _In_ UINT                  Base,
  _In_ UINT                  Count
)
{ ... }
````


## -parameters




### -param D3D10DDI_HRTCORELAYER


### -param UINT








#### - hRuntimeDevice [in]

 A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function. 


#### - Base [in]

 The starting constant buffer to refresh. 


#### - Count [in]

 The total number of buffers to refresh. The number can be -1, which specifies that the Direct3D runtime will use its high watermarks to substitute an optimal value (which is typically less than the maximum valid value for <i>Count</i>). However, no non-NULL binding exists in a slot larger than the optimal <i>Count</i> value. 


## -returns



None




## -remarks



The <i>Base</i> and <i>Count</i> parameters that the driver passes to the <b>pfnStatePsConstBufCb</b> function directly correspond to the <i>StartBuffer</i> and <i>NumBuffers</i> parameters that are passed to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md">PsSetConstantBuffers</a> function.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setconstantbuffers.md">PsSetConstantBuffers</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks.md">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_STATE_PS_CONSTBUF_CB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

