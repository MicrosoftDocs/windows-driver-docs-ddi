---
UID: NF:printerextension.IPrintSchemaParameterDefinition.get_RangeMin
title: IPrintSchemaParameterDefinition::get_RangeMin method
author: windows-driver-content
description: The RangeMin property gets the minimum value of the allowed data range.
old-location: print\_iprintschemaparameterdefinition_rangemin.htm
old-project: print
ms.assetid: ED8A29D9-84CE-4FB5-BCEE-C31DA9AB3D00
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: RangeMin property [Print Devices], RangeMin property [Print Devices], IPrintSchemaParameterDefinition interface, IPrintSchemaParameterDefinition::get_RangeMin, get_RangeMin, IPrintSchemaParameterDefinition.RangeMin, IPrintSchemaParameterDefinition, IPrintSchemaParameterDefinition interface [Print Devices], RangeMin property, printerextension/IPrintSchemaParameterDefinition::get_RangeMin, printerextension/IPrintSchemaParameterDefinition::RangeMin, print._iprintschemaparameterdefinition_rangemin
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	IPrintSchemaParameterDefinition.RangeMin
-	IPrintSchemaParameterDefinition.get_RangeMin
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaParameterDefinition::get_RangeMin method


## -description


The <b>RangeMin</b> property gets the minimum value of the allowed data range.

This property is read-only.


## -syntax


````
HRESULT get_RangeMin(
  [out, retval] INT *pRangeMin
);
````


## -parameters


## -remarks



For the <b>PrintSchemaParameterDataType_Integer</b> data type, the value returned by  <b>RangeMin</b> maps to the &lt;psf:MinValue&gt; property value of the Print Schema parameter definition. This minimum value shows the minimum integer value that the driver supports.

For the <b>PrintSchemaParameterDataType_NumericString</b> and <b>PrintSchemaParameterDataType_String</b>  data types, this maps to the &lt;psf:MinLength&gt; property value of the Print Schema parameter definition. This minimum value shows the minimum length of string that the driver supports.




## -see-also

<a href="..\printerextension\nn-printerextension-iprintschemaparameterdefinition.md">IPrintSchemaParameterDefinition</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaParameterDefinition::RangeMin property%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

