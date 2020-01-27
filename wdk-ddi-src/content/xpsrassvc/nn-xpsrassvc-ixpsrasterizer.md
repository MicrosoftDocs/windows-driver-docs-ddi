---
UID: NN:xpsrassvc.IXpsRasterizer
title: IXpsRasterizer (xpsrassvc.h)
description: The IXpsRasterizer interface represents an XPS rasterizer that can create a bitmap image of an XPS fixed page or of a rectangular region of a fixed page.
old-location: print\ixpsrasterizer_interface.htm
tech.root: print
ms.assetid: 1ef99120-2b3b-45aa-bcf7-16bcb9656089
ms.date: 04/20/2018
ms.keywords: IXpsRasterizer, IXpsRasterizer interface [Print Devices], IXpsRasterizer interface [Print Devices],described, print.ixpsrasterizer_interface, print_xpsrast_e8c45bd1-2f79-4e4f-b6c4-034c703ff173.xml, xpsrassvc/IXpsRasterizer
f1_keywords:
 - "xpsrassvc/IXpsRasterizer"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- xpsrassvc.h
api_name:
- IXpsRasterizer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IXpsRasterizer interface

## -description

The **IXpsRasterizer** interface represents an XPS rasterizer that can create a bitmap image of an XPS fixed page or of a rectangular region of a fixed page.

A client obtains an **IXpsRasterizer** interface instance by calling the [IXpsRasterizationFactory::CreateRasterizer](https://docs.microsoft.com/windows-hardware/drivers/ddi/xpsrassvc/nf-xpsrassvc-ixpsrasterizationfactory-createrasterizer) method.

## -inheritance
