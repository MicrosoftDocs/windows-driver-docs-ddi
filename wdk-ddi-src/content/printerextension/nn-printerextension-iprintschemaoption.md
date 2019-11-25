---
UID: NN:printerextension.IPrintSchemaOption
title: IPrintSchemaOption (printerextension.h)
description: Exposes a Print Schema Option object.
old-location: print\iprintschemaoption_interface.htm
tech.root: print
ms.assetid: B520875A-7882-43D5-A890-0F82654EFD6C
ms.date: 04/20/2018
ms.keywords: IPrintSchemaOption, IPrintSchemaOption interface [Print Devices], IPrintSchemaOption interface [Print Devices],described, print.iprintschemaoption_interface, printerextension/IPrintSchemaOption
ms.topic: interface
f1_keywords:
 - "printerextension/IPrintSchemaOption"
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
- IPrintSchemaOption
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaOption interface


## -description


Exposes a Print Schema Option object.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaOption</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemadisplayableelement">IPrintSchemaDisplayableElement</a>. <b>IPrintSchemaOption</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -remarks



You must ensure that each Feature or Option in a PrintTicket or PrintCapabilities XML document has a <i>name</i> attribute specified. This attribute is used to build the <b>IPrintSchemaOption</b> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemafeature">IPrintSchemaFeature</a> objects. If the <i>name</i> attribute is omitted, the feature or option will not be displayed in the object model, or the Microsoft-provided print preferences experience.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemadisplayableelement">IPrintSchemaDisplayableElement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemafeature-getoption">IPrintSchemaFeature::GetOption</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemafeature-get_selectedoption">IPrintSchemaFeature::SelectedOption</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaoptioncollection">IPrintSchemaOptionCollection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemapagemediasizeoption">IPrintSchemaPageMediaSizeOption</a>
 

 

