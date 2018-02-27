---
UID: NF:printerextension.IPrintSchemaFeature.get_SelectionType
title: IPrintSchemaFeature::get_SelectionType method
author: windows-driver-content
description: Gets the selection type of the Feature.
old-location: print\iprintschemafeature_selectiontype.htm
old-project: print
ms.assetid: FFFF05EF-CCD3-4298-A6DC-8FE998C53DEA
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IPrintSchemaFeature, IPrintSchemaFeature interface [Print Devices], SelectionType property, IPrintSchemaFeature.SelectionType, IPrintSchemaFeature::get_SelectionType, SelectionType property [Print Devices], SelectionType property [Print Devices], IPrintSchemaFeature interface, get_SelectionType, get_SelectionType,IPrintSchemaFeature.get_SelectionType, print.iprintschemafeature_selectiontype, printerextension/IPrintSchemaFeature::SelectionType, printerextension/IPrintSchemaFeature::get_SelectionType
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrintSchemaFeature.SelectionType
-	IPrintSchemaFeature.get_SelectionType
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaFeature::get_SelectionType method


## -description


Gets the selection type of the Feature.

This property is read-only.


## -syntax


````
HRESULT get_SelectionType(
  [out, retval] PrintSchemaSelectionType *pSelectionType
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprintschemafeature.md">IPrintSchemaFeature</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaFeature::SelectionType property%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

