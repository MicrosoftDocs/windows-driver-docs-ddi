---
UID: NF:printerextension.IPrintSchemaParameterDefinition.get_RangeMax
title: IPrintSchemaParameterDefinition::get_RangeMax method
author: windows-driver-content
description: The RangeMax property gets the maximum value of the allowed data range.
old-location: print\_iprintschemaparameterdefinition_rangemax.htm
old-project: print
ms.assetid: 516FADF0-3786-4C41-B38D-4A742AD68719
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintSchemaParameterDefinition, IPrintSchemaParameterDefinition interface [Print Devices], RangeMax property, IPrintSchemaParameterDefinition.RangeMax, IPrintSchemaParameterDefinition::get_RangeMax, RangeMax property [Print Devices], RangeMax property [Print Devices], IPrintSchemaParameterDefinition interface, get_RangeMax, get_RangeMax,IPrintSchemaParameterDefinition.get_RangeMax, print._iprintschemaparameterdefinition_rangemax, printerextension/IPrintSchemaParameterDefinition::RangeMax, printerextension/IPrintSchemaParameterDefinition::get_RangeMax
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrintSchemaParameterDefinition.RangeMax
-	IPrintSchemaParameterDefinition.get_RangeMax
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaParameterDefinition::get_RangeMax method


## -description


The <b>RangeMax</b> property gets the maximum value of the allowed data range.

This property is read-only.


## -syntax


````
HRESULT get_RangeMax(
  [out, retval] INT *pRangeMax
);
````


## -parameters


## -remarks



For the <b>PrintSchemaParameterDataType_Integer</b> data type, the value returned by <b>RangeMax</b> maps to the &lt;psf:MaxValue&gt; property value of the Print Schema parameter definition. This maximum value shows the maximum integer value that the driver supports.

For the <b>PrintSchemaParameterDataType_NumericString</b> and <b>PrintSchemaParameterDataType_String</b>  data types, this maps to the &lt;psf:MaxLength&gt; property value of the Print Schema parameter definition. This maximum value  shows the maximum length of string that the driver supports.




## -see-also

<a href="..\printerextension\nn-printerextension-iprintschemaparameterdefinition.md">IPrintSchemaParameterDefinition</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaParameterDefinition::RangeMax property%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

