---
UID: NN:xpsrassvc.IXpsRasterizerNotificationCallback
title: IXpsRasterizerNotificationCallback (xpsrassvc.h)
description: The IXpsRasterizerNotificationCallback interface enables the XPS rasterization service to determine whether to continue a rasterization operation that was previously initiated by an XPSDrv filter.
old-location: print\ixpsrasterizernotificationcallback_interface.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IXpsRasterizerNotificationCallback interface"]
ms.keywords: IXpsRasterizerNotificationCallback, IXpsRasterizerNotificationCallback interface [Print Devices], IXpsRasterizerNotificationCallback interface [Print Devices],described, print.ixpsrasterizernotificationcallback_interface, print_xpsrast_fe5791b3-111b-454e-a033-45dfa128d325.xml, xpsrassvc/IXpsRasterizerNotificationCallback
req.header: xpsrassvc.h
req.include-header: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IXpsRasterizerNotificationCallback
 - xpsrassvc/IXpsRasterizerNotificationCallback
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - xpsrassvc.h
api_name:
 - IXpsRasterizerNotificationCallback
---

# IXpsRasterizerNotificationCallback interface


## -description

The IXpsRasterizerNotificationCallback interface enables the XPS rasterization service to determine whether to continue a rasterization operation that was previously initiated by an XPSDrv filter. The filter implements this interface and passes an IXpsRasterizerNotificationCallback pointer as a parameter to the [IXpsRasterizer::RasterizeRect](./nf-xpsrassvc-ixpsrasterizer-rasterizerect.md) method.

## -inheritance
