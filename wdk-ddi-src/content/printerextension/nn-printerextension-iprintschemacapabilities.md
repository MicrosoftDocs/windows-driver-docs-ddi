---
UID: NN:printerextension.IPrintSchemaCapabilities
title: IPrintSchemaCapabilities (printerextension.h)
description: Provides the primary method to access PrintCapabilities.
old-location: print\iprintschemacapabilities_interface.htm
tech.root: print
ms.assetid: A148C1B4-99A3-4AF3-B2D6-73684978425F
ms.date: 04/20/2018
ms.keywords: IPrintSchemaCapabilities, IPrintSchemaCapabilities interface [Print Devices], IPrintSchemaCapabilities interface [Print Devices],described, print.iprintschemacapabilities_interface, printerextension/IPrintSchemaCapabilities
ms.topic: interface
f1_keywords:
 - "printerextension/IPrintSchemaCapabilities"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Printerextension.h
api_name:
- IPrintSchemaCapabilities
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaCapabilities interface


## -description


Provides the primary method to access PrintCapabilities.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaCapabilities</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprintschemaelement">IPrintSchemaElement</a>. <b>IPrintSchemaCapabilities</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -members

The <b>IPrintSchemaCapabilities</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschematicket-getfeature">GetFeature</a>
</td>
<td align="left" width="63%">
Gets a named feature from the PrintCapabilities, by name and full namespace URI.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschematicket-getfeaturebykeyname">GetFeatureByKeyName</a>
</td>
<td align="left" width="63%">
Gets a feature from the PrintCapabilities based on a given key name.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemacapabilities-getoptions">GetOptions</a>
</td>
<td align="left" width="63%">
Gets all the options of a feature.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemacapabilities-getselectedoptioninprintticket">GetSelectedOptionInPrintTicket</a>
</td>
<td align="left" width="63%">
Gets the selected option for a feature in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprintschematicket">IPrintSchemaTicket</a>.

</td>
</tr>
</table> 
<h3><a id="properties"></a>Properties</h3>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaCapabilities</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemacapabilities-get_jobcopiesalldocumentsmaxvalue">JobCopiesAllDocumentsMaxValue</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the <b>JobCopiesAllDocuments</b> parameter maximum value.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemacapabilities-get_jobcopiesalldocumentsminvalue">JobCopiesAllDocumentsMinValue</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the <b>JobCopiesAllDocuments</b> parameter minimum value.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemacapabilities-get_pageimageablesize">PageImageableSize</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the imageable area information of the printer.

</td>
</tr>
</table> 


## -remarks



To obtain an IXMLDOMDocument2 object for the PrintCapabilities object, you must first dereference the <i>ppXmlNode</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemaelement-get_xmlnode">XmlNode</a> property (using *ppXmlNode ). This retrieves a pointer to an interface of type <b>IUnknown</b>. Use this pointer to  call the <b>QueryInterface</b> method of the PrintCapabilities object to access the underlying  IXMLDOMDocument2 object.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/print/v4-printer-driver">Developing v4 print drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprintschemaelement">IPrintSchemaElement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemaelement-get_xmlnode">IPrintSchemaElement::XmlNode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprintschematicket">IPrintSchemaTicket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschematicket-getcapabilities">IPrintSchemaTicket_GetCapabilities</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/v4-driver-localization">V4 Printer Driver Localization</a>
 

 

