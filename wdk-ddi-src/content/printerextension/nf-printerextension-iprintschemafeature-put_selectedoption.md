---
UID: NF:printerextension.IPrintSchemaFeature.put_SelectedOption
title: IPrintSchemaFeature::put_SelectedOption method
author: windows-driver-content
description: Changes the selected option of the Print Schema Feature element to the specified IPrintSchemaOption element.
old-location: print\iprintschemafeature_put_selectedoption.htm
old-project: print
ms.assetid: DEFA0559-9946-4F4D-B5DC-A0E5E872114A
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: IPrintSchemaFeature interface [Print Devices], SelectedOption property, printerextension/IPrintSchemaFeature::SelectedOption, SelectedOption property [Print Devices], IPrintSchemaFeature interface, IPrintSchemaFeature, put_SelectedOption, IPrintSchemaFeature::get_SelectedOption, print.iprintschemafeature_put_selectedoption, IPrintSchemaFeature::put_SelectedOption, printerextension/IPrintSchemaFeature::put_SelectedOption, SelectedOption property [Print Devices], get_SelectedOption, IPrintSchemaFeature.SelectedOption
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
-	IPrintSchemaFeature.SelectedOption
-	IPrintSchemaFeature.put_SelectedOption
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaFeature::put_SelectedOption method


## -description


Changes the selected option of the Print Schema Feature element to the specified <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> element.

This property is write-only.


## -syntax


````
HRESULT put_SelectedOption(
   IPrintSchemaOption *pOption
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprintschemafeature.md">IPrintSchemaFeature</a>



<a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaFeature::SelectedOption property%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

