---
UID: NF:printerextension.IPrintSchemaNUpOption.get_PagesPerSheet
title: IPrintSchemaNUpOption::get_PagesPerSheet method
author: windows-driver-content
description: Gets the number of pages per sheet.
old-location: print\iprintschemanupoption_pagespersheet.htm
old-project: print
ms.assetid: 036F59B3-962D-446C-A736-CDA1D5199CF5
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.iprintschemanupoption_pagespersheet, IPrintSchemaNUpOption, PagesPerSheet property [Print Devices], IPrintSchemaNUpOption.PagesPerSheet, IPrintSchemaNUpOption::get_PagesPerSheet, printerextension/IPrintSchemaNUpOption::get_PagesPerSheet, printerextension/IPrintSchemaNUpOption::PagesPerSheet, IPrintSchemaNUpOption interface [Print Devices], PagesPerSheet property, PagesPerSheet property [Print Devices], IPrintSchemaNUpOption interface, get_PagesPerSheet
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
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
-	IPrintSchemaNUpOption.PagesPerSheet
-	IPrintSchemaNUpOption.get_PagesPerSheet
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaNUpOption::get_PagesPerSheet method


## -description


Gets the number of pages per sheet.

This property is read-only.


## -syntax


````
HRESULT get_PagesPerSheet(
  [out, retval] ULONG *pulPagesPerSheet
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprintschemanupoption.md">IPrintSchemaNUpOption</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaNUpOption::PagesPerSheet property%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

