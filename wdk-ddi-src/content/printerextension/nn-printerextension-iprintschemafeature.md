---
UID: NN:printerextension.IPrintSchemaFeature
title: IPrintSchemaFeature (printerextension.h)
description: Exposes a Print Schema Feature element.
tech.root: print
ms.date: 06/11/2021
keywords: ["IPrintSchemaFeature interface"]
ms.keywords: IPrintSchemaFeature, IPrintSchemaFeature interface [Print Devices], IPrintSchemaFeature interface [Print Devices],described, print.iprintschemafeature_interface, printerextension/IPrintSchemaFeature
req.header: printerextension.h
req.include-header: Printerextension.h
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
 - IPrintSchemaFeature
 - printerextension/IPrintSchemaFeature
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaFeature
---

# IPrintSchemaFeature interface

## -description

Exposes a Print Schema Feature element.

## -inheritance

The **IPrintSchemaFeature** interface inherits from [IPrintSchemaDisplayableElement](./nn-printerextension-iprintschemadisplayableelement.md).

## -remarks

You must ensure that each Feature or Option in a PrintTicket or PrintCapabilities XML document has a *name* attribute specified. This attribute is used to build the [IPrintSchemaOption](./nn-printerextension-iprintschemaoption.md) and **IPrintSchemaFeature** objects. If the *name* attribute is omitted, the feature or option will not be displayed in the object model, or the Microsoft-provided print preferences experience.

## -see-also

[IPrintSchemaCapabilities::GetFeature](./nf-printerextension-iprintschemacapabilities-getfeature.md)

[IPrintSchemaDisplayableElement](./nn-printerextension-iprintschemadisplayableelement.md)

[IPrintSchemaTicket::GetFeature](./nf-printerextension-iprintschematicket-getfeature.md)

[IPrintSchemaTicket::GetFeatureByKeyName](./nf-printerextension-iprintschematicket-getfeaturebykeyname.md)