---
UID: NF:printerextension.IPrintSchemaCapabilities.GetSelectedOptionInPrintTicket
title: IPrintSchemaCapabilities::GetSelectedOptionInPrintTicket method
author: windows-driver-content
description: Gets the selected option for a feature in IPrintSchemaTicket.
old-location: print\iprintschemacapabilities_getselectedoptioninprintticket.htm
old-project: print
ms.assetid: 6FAAEDFA-BABC-4406-8A8E-CACFCE3A38B5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetSelectedOptionInPrintTicket method [Print Devices], GetSelectedOptionInPrintTicket method [Print Devices], IPrintSchemaCapabilities interface, GetSelectedOptionInPrintTicket,IPrintSchemaCapabilities.GetSelectedOptionInPrintTicket, IPrintSchemaCapabilities, IPrintSchemaCapabilities interface [Print Devices], GetSelectedOptionInPrintTicket method, IPrintSchemaCapabilities::GetSelectedOptionInPrintTicket, print.iprintschemacapabilities_getselectedoptioninprintticket, printerextension/IPrintSchemaCapabilities::GetSelectedOptionInPrintTicket
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
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
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrintSchemaCapabilities.GetSelectedOptionInPrintTicket
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaCapabilities::GetSelectedOptionInPrintTicket method


## -description


Gets the selected option for a feature in <a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a>.


## -parameters




### -param pFeature [in]

The specified feature.


### -param ppOption [out, retval]

The returned option.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



When the requested feature, option or property is not found, this method returns S_FALSE and sets a NULL pointer on the output object of the feature, option or property.

So if the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a> object does not contain the specified feature, option or property, the app must obtain an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a> object and query it via <a href="https://msdn.microsoft.com/053BFE59-FDC6-42F3-BE14-CE63D5637D62">IPrintSchemaCapabilities::GetFeatureByKeyName</a> or via <a href="https://msdn.microsoft.com/AC6434F5-0892-4426-98BB-BC02AD17917B">IPrintSchemaCapabilities::GetFeature</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a>
 

 

