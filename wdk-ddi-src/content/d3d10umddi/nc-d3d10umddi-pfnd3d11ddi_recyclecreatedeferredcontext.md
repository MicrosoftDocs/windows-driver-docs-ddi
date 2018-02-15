---
UID: NC:d3d10umddi.PFND3D11DDI_RECYCLECREATEDEFERREDCONTEXT
title: PFND3D11DDI_RECYCLECREATEDEFERREDCONTEXT
author: windows-driver-content
description: The RecycleCreateDeferredContext function clears out the pipeline state for a deferred context.
old-location: display\recyclecreatedeferredcontext.htm
old-project: display
ms.assetid: c9e08048-683a-4f43-b3b8-1914c2933a5c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.recyclecreatedeferredcontext, RecycleCreateDeferredContext callback function [Display Devices], RecycleCreateDeferredContext, PFND3D11DDI_RECYCLECREATEDEFERREDCONTEXT, PFND3D11DDI_RECYCLECREATEDEFERREDCONTEXT, d3d10umddi/RecycleCreateDeferredContext, UserModeDisplayDriverDx11_Functions_aaffc9d1-e821-41f9-badc-79d53a667644.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: RecycleCreateDeferredContext is supported beginning with the Windows 7 operating system.
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
-	RecycleCreateDeferredContext
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D11DDI_RECYCLECREATEDEFERREDCONTEXT callback


## -description


The <i>RecycleCreateDeferredContext</i> function clears out the pipeline state for a deferred context.


## -prototype


````
PFND3D11DDI_RECYCLECREATEDEFERREDCONTEXT RecycleCreateDeferredContext;

HRESULT APIENTRY RecycleCreateDeferredContext(
  _In_       D3D10DDI_HDEVICE                  hDevice,
  _In_ const D3D11DDIARG_CREATEDEFERREDCONTEXT *pCreateDeferredContext
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pCreateDeferredContext [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createdeferredcontext.md">D3D11DDIARG_CREATEDEFERREDCONTEXT</a> structure, which describes the parameters that the user-mode display driver uses to create a deferred context. 


## -returns



<i>RecycleCreateDeferredContext</i> returns one of the following values:

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
The deferred context is successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
<i>RecycleCreateDeferredContext</i> could not allocate memory that is required for it to complete.

</td>
</tr>
</table>
 




## -remarks



The driver is only required to implement <i>RecycleCreateDeferredContext</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 threading-capability bit. The driver can return D3D11DDICAPS_COMMANDLISTS_BUILD_2 in the <b>Caps</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a> structure from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a> function.

For more information about <i>RecycleCreateDeferredContext</i>, see <a href="https://msdn.microsoft.com/a417bcc7-ca86-4853-baa3-415214da348f">Introduction to Deferred Contexts</a>.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createdeferredcontext.md">D3D11DDIARG_CREATEDEFERREDCONTEXT</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_RECYCLECREATEDEFERREDCONTEXT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

