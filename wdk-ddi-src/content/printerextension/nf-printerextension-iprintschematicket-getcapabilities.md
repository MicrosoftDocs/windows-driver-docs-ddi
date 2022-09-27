---
UID: NF:printerextension.IPrintSchemaTicket.GetCapabilities
title: IPrintSchemaTicket::GetCapabilities (printerextension.h)
description: Gets an IPrintSchemaCapabilities object that represents the printer capabilities based on the current settings of this IPrintSchemaTicket object.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrintSchemaTicket::GetCapabilities"]
ms.keywords: GetCapabilities, GetCapabilities method [Print Devices], GetCapabilities method [Print Devices],IPrintSchemaTicket interface, IPrintSchemaTicket, IPrintSchemaTicket interface [Print Devices],GetCapabilities method, IPrintSchemaTicket.GetCapabilities, IPrintSchemaTicket::GetCapabilities, print.iprintschematicket_getcapabilities, printerextension/IPrintSchemaTicket::GetCapabilities
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintSchemaTicket::GetCapabilities
 - printerextension/IPrintSchemaTicket::GetCapabilities
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - printerextension.h
api_name:
 - IPrintSchemaTicket::GetCapabilities
---

## -description

Gets an [IPrintSchemaCapabilities](./nn-printerextension-iprintschemacapabilities.md) object that represents the printer capabilities based on the current settings of this [IPrintSchemaTicket](./nn-printerextension-iprintschematicket.md) object.

## -parameters

### -param ppCapabilities

The returned [IPrintSchemaCapabilities](./nn-printerextension-iprintschemacapabilities.md) object.

## -returns

This method returns an **HRESULT** value.

## -remarks

Because this method retrieves a new PrintCapabilities document every time it is invoked, it is recommended that you invoke this method only when the [IPrintSchemaTicket](./nn-printerextension-iprintschematicket.md) object has been modified.

## -see-also

[IPrintSchemaCapabilities](./nn-printerextension-iprintschemacapabilities.md)

[IPrintSchemaElement::XmlNode](./nf-printerextension-iprintschemaelement-get_xmlnode.md)

[IPrintSchemaFeature::SelectedOption](./nf-printerextension-iprintschemafeature-get_selectedoption.md)

[IPrintSchemaTicket](./nn-printerextension-iprintschematicket.md)

[IPrintSchemaTicket::put_JobCopiesAllDocuments](/windows/win32/api/rrascfg/nf-rrascfg-ieapproviderconfig-initialize)