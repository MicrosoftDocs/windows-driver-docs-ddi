---
UID: NE:xpsrassvc.__MIDL___MIDL_itf_xpsrassvc_0000_0001_0001
title: __MIDL___MIDL_itf_xpsrassvc_0000_0001_0001 (xpsrassvc.h)
description: The XPSRAS_RENDERING_MODE enumeration specifies the rendering mode to be used by an XPS rasterizer.
old-location: print\xpsras_rendering_mode_enumeration.htm
tech.root: print
ms.assetid: 8b0b2bde-6ada-4a73-9737-7150605b79c8
ms.date: 04/20/2018
keywords: ["_MIDL___MIDL_itf_xpsrassvc_0000_0001_0001 enumeration"]
ms.keywords: XPSRAS_RENDERING_MODE, XPSRAS_RENDERING_MODE enumeration [Print Devices], XPSRAS_RENDERING_MODE_ALIASED, XPSRAS_RENDERING_MODE_ANTIALIASED, __MIDL___MIDL_itf_xpsrassvc_0000_0001_0001, print.xpsras_rendering_mode_enumeration, print_xpsrast_7ef89e32-be23-4164-8f23-33ce5db681dd.xml, xpsrassvc/XPSRAS_RENDERING_MODE, xpsrassvc/XPSRAS_RENDERING_MODE_ALIASED, xpsrassvc/XPSRAS_RENDERING_MODE_ANTIALIASED
f1_keywords:
 - "xpsrassvc/XPSRAS_RENDERING_MODE"
 - "XPSRAS_RENDERING_MODE"
req.header: xpsrassvc.h
req.include-header: Xpsrassvc.h
req.target-type: Windows
req.target-min-winverclnt: Windows 7
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- xpsrassvc.h
api_name:
- XPSRAS_RENDERING_MODE
targetos: Windows
req.typenames: XPSRAS_RENDERING_MODE
---

# __MIDL___MIDL_itf_xpsrassvc_0000_0001_0001 enumeration


## -description


The XPSRAS_RENDERING_MODE enumeration specifies the rendering mode to be used by an XPS rasterizer.


## -enum-fields




### -field XPSRAS_RENDERING_MODE_ANTIALIASED

Use antialiasing to rasterize the specified graphics elements.


### -field XPSRAS_RENDERING_MODE_ALIASED

Do not use antialiasing to rasterize the specified graphics elements.


## -remarks



The values defined in this enumeration are used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nf-xpsrassvc-ixpsrasterizationfactory-createrasterizer">IXpsRasterizationFactory::CreateRasterizer</a> method.

For more information about rasterizing XPS documents, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/using-the-xps-rasterization-service">Using the XPS Rasterization Service</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nf-xpsrassvc-ixpsrasterizationfactory-createrasterizer">IXpsRasterizationFactory::CreateRasterizer</a>
 

 

