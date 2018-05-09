---
UID: NF:printerextension.IPrintSchemaCapabilities.GetFeatureByKeyName
title: IPrintSchemaCapabilities::GetFeatureByKeyName
author: windows-driver-content
description: Gets a feature from the PrintCapabilities based on a given key name.
old-location: print\iprintschemacapabilities_getfeaturebykeyname.htm
old-project: print
ms.assetid: 053BFE59-FDC6-42F3-BE14-CE63D5637D62
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: GetFeatureByKeyName, GetFeatureByKeyName method [Print Devices], GetFeatureByKeyName method [Print Devices],IPrintSchemaCapabilities interface, IPrintSchemaCapabilities, IPrintSchemaCapabilities interface [Print Devices],GetFeatureByKeyName method, IPrintSchemaCapabilities.GetFeatureByKeyName, IPrintSchemaCapabilities::GetFeatureByKeyName, print.iprintschemacapabilities_getfeaturebykeyname, printerextension/IPrintSchemaCapabilities::GetFeatureByKeyName
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
-	IPrintSchemaCapabilities.GetFeatureByKeyName
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaCapabilities::GetFeatureByKeyName


## -description


Gets a feature from the PrintCapabilities based on a given key name.


## -parameters




### -param bstrKeyName [in]

The key name of the feature.


### -param ppFeature [out, retval]

The returned feature.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



Only the following feature key names are recognized. The key names are equivalent to public Print Schema feature names as shown in the following table. The table also shows the features that have specialized option types (by default the option type is <a href="https://msdn.microsoft.com/library/windows/hardware/hh451335">IPrintSchemaOption</a>).

<table>
<tr>
<th>Name</th>
<th>Print schema feature public name</th>
<th>Specialized option type</th>
</tr>
<tr>
<td>DocumentBinding</td>
<td>DocumentBinding or JobBindAllDocuments</td>
<td></td>
</tr>
<tr>
<td>DocumentCollate</td>
<td>DocumentCollate</td>
<td></td>
</tr>
<tr>
<td>DocumentDuplex</td>
<td>JobDuplexAllDocumentsContiguously</td>
<td></td>
</tr>
<tr>
<td>DocumentHolePunch</td>
<td>DocumentHolePunch or JobHolePunch</td>
<td></td>
</tr>
<tr>
<td>DocumentInputBin</td>
<td>JobInputBin, DocumentInputBin or PageInputBin</td>
<td></td>
</tr>
<tr>
<td>DocumentNUp</td>
<td>JobNUpAllDocumentsContiguously</td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451302">IPrintSchemaNUpOption</a>
</td>
</tr>
<tr>
<td>DocumentStaple</td>
<td>JobStapleAllDocuments or DocumentStaple</td>
<td></td>
</tr>
<tr>
<td>PageMediaSize</td>
<td>PageMediaSize</td>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451378">IPrintSchemaPageMediaSizeOption</a>
</td>
</tr>
<tr>
<td>PageMediaType</td>
<td>PageMediaType</td>
<td></td>
</tr>
<tr>
<td>PageOrientation</td>
<td>PageOrientation</td>
<td></td>
</tr>
<tr>
<td>PageOutputColor</td>
<td>PageOutputColor</td>
<td></td>
</tr>
<tr>
<td>PageOutputQuality</td>
<td>PageOutputQuality</td>
<td></td>
</tr>
</table>
 

When the requested feature, option or property is not found, this method returns S_FALSE and sets a NULL pointer on the output object of the feature, option or property.

So if the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a> object does not contain the specified feature, option or property, the app must obtain an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a> object and query it via <b>IPrintSchemaCapabilities::GetFeatureByKeyName</b> or via <a href="https://msdn.microsoft.com/AC6434F5-0892-4426-98BB-BC02AD17917B">IPrintSchemaCapabilities::GetFeature</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451302">IPrintSchemaNUpOption</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451335">IPrintSchemaOption</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451378">IPrintSchemaPageMediaSizeOption</a>
 

 

