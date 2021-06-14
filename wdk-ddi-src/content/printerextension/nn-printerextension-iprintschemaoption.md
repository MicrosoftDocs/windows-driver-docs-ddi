---
UID: NN:printerextension.IPrintSchemaOption
title: IPrintSchemaOption (printerextension.h)
description: Exposes a Print Schema Option object.
tech.root: print
ms.date: 06/11/2021
keywords: ["IPrintSchemaOption interface"]
ms.keywords: IPrintSchemaOption, IPrintSchemaOption interface [Print Devices], IPrintSchemaOption interface [Print Devices],described, print.iprintschemaoption_interface, printerextension/IPrintSchemaOption
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintSchemaOption
 - printerextension/IPrintSchemaOption
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaOption
---

# IPrintSchemaOption interface

## -description

Exposes a Print Schema Option object.

## -inheritance

The **IPrintSchemaOption** interface inherits from [IPrintSchemaDisplayableElement](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemadisplayableelement).

## -remarks

You must ensure that each Feature or Option in a PrintTicket or PrintCapabilities XML document has a *name* attribute specified. This attribute is used to build the **IPrintSchemaOption** and [IPrintSchemaFeature](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemafeature) objects. If the *name* attribute is omitted, the feature or option will not be displayed in the object model, or the Microsoft-provided print preferences experience.

## -see-also

[IPrintSchemaDisplayableElement](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemadisplayableelement)

[IPrintSchemaFeature::GetOption](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemafeature-getoption)

[IPrintSchemaFeature::SelectedOption](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemafeature-get_selectedoption)

[IPrintSchemaOptionCollection](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaoptioncollection)

[IPrintSchemaPageMediaSizeOption](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemapagemediasizeoption)
