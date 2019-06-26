---
UID: NN:printerextension.IPrintSchemaTicket
title: IPrintSchemaTicket (printerextension.h)
description: Provides the primary method to access and validate a PrintTicket.
old-location: print\iprintschematicket_interface.htm
tech.root: print
ms.assetid: 190B0B88-6018-4B43-8699-78427421D6FF
ms.date: 10/19/2018
ms.keywords: IPrintSchemaTicket, IPrintSchemaTicket interface [Print Devices], IPrintSchemaTicket interface [Print Devices],described, print.iprintschematicket_interface, printerextension/IPrintSchemaTicket
ms.topic: interface
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
- IPrintSchemaTicket
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaTicket interface


## -description


Provides the primary method to access and validate a PrintTicket.


## -inheritance

The **IPrintSchemaTicket** interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprintschemaelement">IPrintSchemaElement</a>. **IPrintSchemaTicket** also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -members

The <b>IPrintSchemaTicket</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschematicket-commitasync">CommitAsync</a>
</td>
<td align="left" width="63%">
Gets an  asynchronous PrintTicket commit operation context.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschematicket-getcapabilities">GetCapabilities</a>
</td>
<td align="left" width="63%">
Gets an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprintschemacapabilities">IPrintSchemaCapabilities</a> object that represents the printer capabilities based on the current settings of this <b>IPrintSchemaTicket</b> object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschematicket-getfeature">GetFeature</a>
</td>
<td align="left" width="63%">
Gets a named feature from the PrintTicket, by name and full namespace URI.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschematicket-getfeaturebykeyname">GetFeatureByKeyName</a>
</td>
<td align="left" width="63%">
Gets a feature from the PrintTicket based on the specified key name.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschematicket-notifyxmlchanged">NotifyXmlChanged</a>
</td>
<td align="left" width="63%">
Notifies the print system that the XML DOM object has changed.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschematicket-validateasync">ValidateAsync</a>
</td>
<td align="left" width="63%">
Gets an asynchronous PrintTicket validation operation context.

</td>
</tr>
</table> 
<h3><a id="properties"></a>Properties</h3>The **IPrintSchemaTicket** interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows/desktop/api/rrascfg/nf-rrascfg-ieapproviderconfig-initialize">JobCopiesAllDocuments</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the copy count.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://docs.microsoft.com/windows/desktop/api/rrascfg/nf-rrascfg-ieapproviderconfig-initialize">JobCopiesAllDocuments</a>


</td>
<td align="left" width="10%">
Write-only

</td>
<td align="left" width="63%">
Sets the copy count.

</td>
</tr>
</table> 


## -remarks

For C++ clients, to obtain an IXMLDOMDocument2 object for the PrintTicket object, you must first dereference the <i>ppXmlNode</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemaelement-get_xmlnode">XmlNode</a> property (using *ppXmlNode ). This retrieves a pointer to an interface of type <b>IUnknown</b>. Use this pointer to  call the <b>QueryInterface</b> method of the PrintTicket object to access the underlying IXMLDOMDocument2 object.

For C# and JavaScript clients, use printerextension.h GetReadStream or GetWriteStream methods to access a IPrintSchemaElement XmlNode.

## -see-also

[IPrintSchemaAsyncOperationEvent::Completed](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemaasyncoperationevent-completed)

[IPrintSchemaCapabilities](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprintschemacapabilities)

[IPrintSchemaElement](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprintschemaelement)

[IPrintSchemaElement::XmlNode](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemaelement-get_xmlnode)
 
