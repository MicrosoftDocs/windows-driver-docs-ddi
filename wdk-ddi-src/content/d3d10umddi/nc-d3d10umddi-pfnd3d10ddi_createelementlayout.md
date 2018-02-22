---
UID: NC:d3d10umddi.PFND3D10DDI_CREATEELEMENTLAYOUT
title: PFND3D10DDI_CREATEELEMENTLAYOUT
author: windows-driver-content
description: The CreateElementLayout function creates an element layout.
old-location: display\createelementlayout.htm
old-project: display
ms.assetid: 5af2189a-a064-4c62-be09-733c1d632983
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.createelementlayout, CreateElementLayout callback function [Display Devices], CreateElementLayout, PFND3D10DDI_CREATEELEMENTLAYOUT, PFND3D10DDI_CREATEELEMENTLAYOUT, d3d10umddi/CreateElementLayout, UserModeDisplayDriverDx10_Functions_ca001144-74f8-4ff7-9cce-664d4070ad3d.xml
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
-	CreateElementLayout
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D10DDI_CREATEELEMENTLAYOUT callback


## -description


The <b>CreateElementLayout</b> function creates an element layout.


## -prototype


````
PFND3D10DDI_CREATEELEMENTLAYOUT CreateElementLayout;

VOID APIENTRY CreateElementLayout(
  _In_       D3D10DDI_HDEVICE                hDevice,
  _In_ const D3D10DDIARG_CREATEELEMENTLAYOUT *pCreateElementLayout,
  _In_       D3D10DDI_HELEMENTLAYOUT         hElementLayout,
  _In_       D3D10DDI_HRTELEMENTLAYOUT       hRTElementLayout
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *


### -param D3D10DDI_HELEMENTLAYOUT


### -param D3D10DDI_HRTELEMENTLAYOUT








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pCreateElementLayout [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createelementlayout.md">D3D10DDIARG_CREATEELEMENTLAYOUT</a> structure that describes the parameters that the user-mode display driver uses to create an element layout. 


#### - hElementLayout [in]

 A handle to the driver's private data for the element layout. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateelementlayoutsize.md">CalcPrivateElementLayoutSize</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its element layout object. 


#### - hRTElementLayout [in]

 A handle to the element layout that the driver should use anytime it calls back into the Direct3D runtime. 


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyelementlayout.md">DestroyElementLayout</a> function to destroy the handle that the <i>hElementLayout</i> parameter specifies.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createelementlayout.md">D3D10DDIARG_CREATEELEMENTLAYOUT</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyelementlayout.md">DestroyElementLayout</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateelementlayoutsize.md">CalcPrivateElementLayoutSize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CREATEELEMENTLAYOUT callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

