---
UID: NN:printerextension.IPrintSchemaPageImageableSize
title: IPrintSchemaPageImageableSize
author: windows-driver-content
description: Exposes the PageImageableSize property of PrintCapabilities. The properties of this interface map directly to those in the PageImageableSize property of PrintCapabilities.
old-location: print\iprintschemapageimageablesize_interface.htm
old-project: print
ms.assetid: C8E9278D-D24A-4EEC-8F68-D77C76ECCC40
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintSchemaTicket2, IPrintSchemaTicket2::GetParameterInitializer, GetParameterInitializer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintSchemaPageImageableSize
req.alt-loc: Printerextension.h
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
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaPageImageableSize interface



## -description
Exposes the PageImageableSize property of PrintCapabilities. The properties of this interface map directly to those in the PageImageableSize property of PrintCapabilities.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaPageImageableSize</b> interface inherits from <a href="..\printerextension\nn-printerextension-iprintschemaelement.md">IPrintSchemaElement</a>. <b>IPrintSchemaPageImageableSize</b> also has these types of members:

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaPageImageableSize</b> interface has these properties.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh973229">ExtentHeightInMicrons</a>


Read-only

Gets the vertical distance between the origin and the bounding limit of the canvas application media size.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh973230">ExtentWidthInMicrons</a>


Read-only

Gets the horizontal distance between the origin and the bounding limit of the application media size.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh973231">ImageableSizeHeightInMicrons</a>


Read-only

Gets the vertical dimension of the application media size relative to the page orientation.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh973232">ImageableSizeWidthInMicrons</a>


Read-only

Gets the horizontal dimension of the application media size relative to the page orientation.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh973233">OriginHeightInMicrons</a>


Read-only

Gets the vertical origin of the imageable area relative to the application media size.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh973234">OriginWidthInMicrons</a>


Read-only

Gets the horizontal origin of the imageable area relative to the application media size.

 


## -remarks
