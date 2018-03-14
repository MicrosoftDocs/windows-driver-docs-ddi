---
UID: NF:printerextension.IPrintSchemaCapabilities.get_PageImageableSize
title: IPrintSchemaCapabilities::get_PageImageableSize method
author: windows-driver-content
description: Gets the imageable area information of the printer.
old-location: print\iprintschemacapabilities_pageimageablesize.htm
old-project: print
ms.assetid: 5FA7613C-8714-481D-8439-9F3334D2E9E5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintSchemaCapabilities, IPrintSchemaCapabilities interface [Print Devices], PageImageableSize property, IPrintSchemaCapabilities.PageImageableSize, IPrintSchemaCapabilities::get_PageImageableSize, PageImageableSize property [Print Devices], PageImageableSize property [Print Devices], IPrintSchemaCapabilities interface, get_PageImageableSize, get_PageImageableSize,IPrintSchemaCapabilities.get_PageImageableSize, print.iprintschemacapabilities_pageimageablesize, printerextension/IPrintSchemaCapabilities::PageImageableSize, printerextension/IPrintSchemaCapabilities::get_PageImageableSize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrintSchemaCapabilities.PageImageableSize
-	IPrintSchemaCapabilities.get_PageImageableSize
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaCapabilities::get_PageImageableSize method


## -description


Gets the imageable area information of the printer.

This property is read-only.


## -syntax


````
HRESULT get_PageImageableSize(
  [out, retval] IPrintSchemaPageImageableSize **ppPageImageableSize
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprintschemapageimageablesize.md">IPrintSchemaPageImageableSize</a>



<a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaCapabilities::PageImageableSize property%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

