---
UID: NC:d3d10umddi.PFND3D11DDI_CALCDEFERREDCONTEXTHANDLESIZE
title: PFND3D11DDI_CALCDEFERREDCONTEXTHANDLESIZE
author: windows-driver-content
description: The CalcDeferredContextHandleSize function queries for the amount of storage space that the driver requires to satisfy deferred context handles to the given immediate context object.
old-location: display\calcdeferredcontexthandlesize.htm
old-project: display
ms.assetid: d26c26ef-be8e-434a-b3d3-623ed539c541
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: CalcDeferredContextHandleSize, CalcDeferredContextHandleSize callback function [Display Devices], PFND3D11DDI_CALCDEFERREDCONTEXTHANDLESIZE, UserModeDisplayDriverDx11_Functions_f5e77e2c-2925-4556-b80a-84636a4b326a.xml, d3d10umddi/CalcDeferredContextHandleSize, display.calcdeferredcontexthandlesize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcDeferredContextHandleSize is supported beginning with the Windows 7 operating system.
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
-	d3d10umddi.h
api_name:
-	CalcDeferredContextHandleSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_CALCDEFERREDCONTEXTHANDLESIZE callback


## -description


The <b>CalcDeferredContextHandleSize</b> function queries for the amount of storage space that the driver requires to satisfy deferred context handles to the given immediate context object. 


## -prototype


````
PFND3D11DDI_CALCDEFERREDCONTEXTHANDLESIZE CalcDeferredContextHandleSize;

SIZE_T APIENTRY CalcDeferredContextHandleSize(
  _In_ D3D10DDI_HDEVICE    hDevice,
  _In_ D3D11DDI_HANDLETYPE HandleType,
  _In_ VOID                *pICObject
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D11DDI_HANDLETYPE


### -param *








#### - HandleType [in]

 A <a href="..\d3d10umddi\ne-d3d10umddi-d3d11ddi_handletype.md">D3D11DDI_HANDLETYPE</a>-typed value that indicates the type of deferred context handle to determine the size of the memory region for. 


#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pICObject [in]

 A pointer to the object for the immediate context.


## -returns



<b>CalcDeferredContextHandleSize</b> returns the size of the storage space that the driver requires for the deferred context handles to the object that <b>pICObject</b> points to.




## -remarks



The driver is only required to implement <b>CalcDeferredContextHandleSize</b> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability that can be returned in the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a> structure from a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a> function.

The Direct3D runtime does not call the <b>CalcDeferredContextHandleSize</b> function from function tables for the deferred context. The runtime calls <b>CalcDeferredContextHandleSize</b> from the function table for the immediate context.

For more information about how <b>CalcDeferredContextHandleSize</b> is used, see <a href="https://msdn.microsoft.com/1b3e5c29-9b9e-4c10-8fe0-706255c8fd91">Using Context-Local DDI Handles</a>. 




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d11ddi_handletype.md">D3D11DDI_HANDLETYPE</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_CALCDEFERREDCONTEXTHANDLESIZE callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

