---
UID: NN:printerextension.IPrintSchemaFeature
title: IPrintSchemaFeature (printerextension.h)
description: Exposes a Print Schema Feature element.
old-location: print\iprintschemafeature_interface.htm
tech.root: print
ms.assetid: AAC2A60B-9E70-4809-969A-68783A91B093
ms.date: 04/20/2018
ms.keywords: IPrintSchemaFeature, IPrintSchemaFeature interface [Print Devices], IPrintSchemaFeature interface [Print Devices],described, print.iprintschemafeature_interface, printerextension/IPrintSchemaFeature
f1_keywords:
 - "printerextension/IPrintSchemaFeature"
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
- IPrintSchemaFeature
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaFeature interface


## -description


Exposes a Print Schema Feature element.


## -inheritance

The <b xmlns:loc="https://microsoft.com/wdcml/l10n">IPrintSchemaFeature</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemadisplayableelement">IPrintSchemaDisplayableElement</a>. <b>IPrintSchemaFeature</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -remarks



You must ensure that each Feature or Option in a PrintTicket or PrintCapabilities XML document has a <i>name</i> attribute specified. This attribute is used to build the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaoption">IPrintSchemaOption</a> and <b>IPrintSchemaFeature</b> objects. If the <i>name</i> attribute is omitted, the feature or option will not be displayed in the object model, or the Microsoft-provided print preferences experience.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemacapabilities-getfeature">IPrintSchemaCapabilities::GetFeature</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemadisplayableelement">IPrintSchemaDisplayableElement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschematicket-getfeature">IPrintSchemaTicket::GetFeature</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschematicket-getfeaturebykeyname">IPrintSchemaTicket::GetFeatureByKeyName</a>
 

 

