---
UID: NF:prdrvcom.IPrintTicketProvider2.ConvertDevModeToPrintTicket
tech.root: print
title: IPrintTicketProvider2::ConvertDevModeToPrintTicket (prdrvcom.h)
ms.date: 08/25/2022
targetos: Windows
description: The IPrintTicketProvider2::ConvertDevModeToPrintTicket method converts a DEVMODEW structure into a print ticket.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: prdrvcom.h
req.idl: 
req.include-header: Prdrvcom.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - prdrvcom.h
api_name:
 - IPrintTicketProvider2::ConvertDevModeToPrintTicket
f1_keywords:
 - IPrintTicketProvider2::ConvertDevModeToPrintTicket
 - prdrvcom/IPrintTicketProvider2::ConvertDevModeToPrintTicket
dev_langs:
 - c++
helpviewer_keywords:
 - ConvertDevModeToPrintTicket
---

## -description

The **IPrintTicketProvider2::ConvertDevModeToPrintTicket** method converts a **DEVMODEW** structure into a print ticket.

## -parameters

### -param cbDevmode [in]

The size, in bytes, of the input **DEVMODEW** structure. The size includes both the public and private portions of this structure.

### -param pDevmode [in]

A pointer to the input **DEVMODEW** structure, including its public and private portions.

### -param pPrintTicket [in]

A pointer to the partially-completed print ticket. When **IPrintTicketProvider2::ConvertDevModeToPrintTicket** returns, all entries in the print ticket should be filled in.

## -returns

**IPrintTicketProvider2::ConvertDevModeToPrintTicket** should return **S_OK** if the operation succeeds. Otherwise, this method should return a standard COM error code.

## -remarks

When the print system converts the contents of a **DEVMODEW** structure into a print ticket, it converts all of the public **DEVMODEW** fields except those that the plug-in provider has indicated should be disabled. For these **DEVMODEW** fields that are disabled and not converted, the plug-in provider is responsible for populating the corresponding print ticket values. If the **DEVMODEW** snapshot was disabled during a call to IPrintTicketProvider2::BindPrinter, the representation from the conversion must provide enough information to reconstruct the original **DEVMODEW** structure from the print ticket without loss of information.

The DEVMODEW snapshot allows support for subtle distinctions in options provided in the **DEVMODEW** structure for which the print ticket might not have representations. For example, **DEVMODEW** might support the LETTER paper size while the print ticket supports the LETTERSMALL paper size.

## -see-also

[IPrintTicketProvider2](./nn-prdrvcom-iprintticketprovider2.md)

[IPrintTicketProvider2::ConvertPrintTicketToDevMode](./nf-prdrvcom-iprintticketprovider2-convertprinttickettodevmode.md)
