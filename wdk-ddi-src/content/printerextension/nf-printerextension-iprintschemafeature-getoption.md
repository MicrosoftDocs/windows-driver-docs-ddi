---
UID: NF:printerextension.IPrintSchemaFeature.GetOption
title: IPrintSchemaFeature::GetOption
author: windows-driver-content
description: Gets the option with the given name.
old-location: print\iprintschemafeature_getoption.htm
tech.root: print
ms.assetid: C9C4E085-1F2A-4610-AF2A-8F87E5CE7BCA
ms.date: 4/20/2018
ms.keywords: GetOption, GetOption method [Print Devices], GetOption method [Print Devices],IPrintSchemaFeature interface, IPrintSchemaFeature, IPrintSchemaFeature interface [Print Devices],GetOption method, IPrintSchemaFeature.GetOption, IPrintSchemaFeature::GetOption, print.iprintschemafeature_getoption, printerextension/IPrintSchemaFeature::GetOption
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
-	IPrintSchemaFeature.GetOption
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaFeature::GetOption


## -description


Gets the option with the given name.


## -parameters




### -param bstrName [in]

The name of the option.


### -param bstrNamespaceUri [in]

The namespace URI of the option.


### -param ppOption [out, retval]

The returned option.


## -returns



This method returns an <b>HRESULT</b> value, if the call was successful. Otherwise it returns the appropriate error code.




## -remarks



When the requested feature, option or property is not found, this method returns S_FALSE and sets a NULL pointer on the output object of the feature, option or property.

So if the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a> object does not contain the specified feature, option or property, the app must obtain an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a> object and query it via <a href="https://msdn.microsoft.com/053BFE59-FDC6-42F3-BE14-CE63D5637D62">IPrintSchemaCapabilities::GetFeatureByKeyName</a> or via <a href="https://msdn.microsoft.com/AC6434F5-0892-4426-98BB-BC02AD17917B">IPrintSchemaCapabilities::GetFeature</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451284">IPrintSchemaFeature</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451335">IPrintSchemaOption</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a>
 

 

