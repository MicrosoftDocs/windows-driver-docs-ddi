---
UID: NF:printerextension.IPrintSchemaOption.GetPropertyValue
title: IPrintSchemaOption::GetPropertyValue
author: windows-driver-content
description: Gets the XML node for the &#0034;value&#0034; child element of a &#0034;Property&#0034; or a &#0034;ScoredProperty&#0034; element with the given name.
old-location: print\iprintschemaoption_getpropertyvalue.htm
old-project: print
ms.assetid: 6CD5202C-7852-46AA-90ED-3477E6654188
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: GetPropertyValue, GetPropertyValue method [Print Devices], GetPropertyValue method [Print Devices],IPrintSchemaOption interface, IPrintSchemaOption, IPrintSchemaOption interface [Print Devices],GetPropertyValue method, IPrintSchemaOption.GetPropertyValue, IPrintSchemaOption::GetPropertyValue, print.iprintschemaoption_getpropertyvalue, printerextension/IPrintSchemaOption::GetPropertyValue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
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
-	IPrintSchemaOption.GetPropertyValue
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaOption::GetPropertyValue


## -description


Gets the XML node for the "value" child element of a "Property"  or a "ScoredProperty" element with the given name.


## -parameters




### -param bstrName [in]

The base value of the "name" attribute of the "Property" or the "ScoredProperty" element.


### -param bstrNamespaceUri [in]

The namespace URI value of the "name" attribute of the "Property" or the "ScoredProperty" element.


### -param ppXmlValueNode






#### - ppXmlNodeValue [out, retval]

The XML node for the "value" child element.


## -returns



Returns an <b>HRESULT</b> value. If the method call was not successful,  it returns the appropriate <b>HRESULT</b> error code.




## -remarks



When the requested feature, option or property is not found, this method returns S_FALSE and sets a NULL pointer on the output object of the feature, option or property.

So if the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a> object does not contain the specified feature, option or property, the app must obtain an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a> object and query it via <a href="https://msdn.microsoft.com/053BFE59-FDC6-42F3-BE14-CE63D5637D62">IPrintSchemaCapabilities::GetFeatureByKeyName</a> or via <a href="https://msdn.microsoft.com/AC6434F5-0892-4426-98BB-BC02AD17917B">IPrintSchemaCapabilities::GetFeature</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451335">IPrintSchemaOption</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a>
 

 

