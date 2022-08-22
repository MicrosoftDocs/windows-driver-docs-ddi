---
UID: NF:prdrvcom.ConvertPrintTicketToDevMode
title: ConvertPrintTicketToDevMode function (prdrvcom.h)
description: The IPrintOemPrintTicketProvider::ConvertPrintTicketToDevMode method converts a print ticket to a DEVMODEW structure.
tech.root: print
ms.date: 08/22/2022
keywords: ["ConvertPrintTicketToDevMode function"]
ms.keywords: ConvertPrintTicketToDevMode, ConvertPrintTicketToDevMode method [Print Devices], ConvertPrintTicketToDevMode method [Print Devices],IPrintOemPrintTicketProvider interface, IPrintOemPrintTicketProvider interface [Print Devices],ConvertPrintTicketToDevMode method, IPrintOemPrintTicketProvider::ConvertPrintTicketToDevMode, prdrvcom/IPrintOemPrintTicketProvider::ConvertPrintTicketToDevMode, print.IPrintOemPrintTicketProvider_convertprinttickettodevmode, print_ticket-package_5d7b3ff3-0c39-4896-986a-ae2306543644.xml
f1_keywords:
 - "prdrvcom/IPrintOemPrintTicketProvider.ConvertPrintTicketToDevMode"
 - "IPrintOemPrintTicketProvider.ConvertPrintTicketToDevMode"
req.header: prdrvcom.h
req.include-header: Prdrvcom.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- prdrvcom.h
api_name:
- IPrintOemPrintTicketProvider.ConvertPrintTicketToDevMode
targetos: Windows
req.typenames: 
---

## -description

The **IPrintOemPrintTicketProvider::ConvertPrintTicketToDevMode** method converts a print ticket to a [DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure.

## -parameters

### -param pPrintTicket [in]

A pointer to the input print ticket. **IPrintOemPrintTicketProvider::ConvertPrintTicketToDevMode** converts the settings in the input print ticket into fields in the [DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure.

### -param cbDevmodeIn [in]

The size, in bytes, of the input DEVMODEW structure. This size includes both the public and private sections of the DEVMODEW structure.

### -param pDevmodeIn [in]

A pointer to the input DEVMODEW structure, which contains default settings. The DEVMODEW structure can be the print queue default DEVMODEW structure, or it can be the user default DEVMODEW structure. Because this parameter can represent the user default DEVMODEW structure, the OEM plug-in provider must validate the data in that  structure. A user default DEVMODEW structure might not be valid for a specific driver, for example, when the print queue's driver changes or is upgraded.

### -param pcbDevmodeOut [out]

A pointer to a variable that contains the size, in bytes, of the output [DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure.

### -param ppDevmodeOut [out]

A pointer to a variable that contains the address of the output DEVMODEW structure. When **IPrintOemPrintTicketProvider::ConvertPrintTicketToDevMode** successfully returns, the members of the output DEVMODEW structure will be reset to reflect the settings in the print ticket. For more information, see the following Remarks section.

## -returns

**IPrintOemPrintTicketProvider::ConvertPrintTicketToDevMode** should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.

## -remarks

The core driver calls the **IPrintOemPrintTicketProvider::ConvertPrintTicketToDevMode** method before it performs its part of the conversion of a print ticket to a [DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure. In the call to this method, the core driver passes an input print ticket that is fully populated and a DEVMODEW structure that is set to default values. In the conversion, the plug-in must undo any changes that it made to the print ticket during the previous conversion from a DEVMODEW structure to a print ticket. If, during this previous conversion, the plug-in moved a feature from a private namespace to the public namespace, the plug-in must restore the feature to the private namespace in a format that is suitable for the core driver, that is, to the format in which the core driver had previously placed the feature in the print ticket that was provided to the plug-in in the [IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket](../prcomoem/nf-prcomoem-iprintoemprintticketprovider-convertdevmodetoprintticket.md) method. This restoration is necessary so that the core driver can recognize a feature in the print ticket and reflect its settings in the private portion of the core driver's DEVMODEW structure while the core driver performs its part of the print ticket-to-DEVMODEW conversion.

Before the system converts a print ticket back to a [DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure, it first loads the default DEVMODEW. The system then calls the provider's [IPrintOemPrintTicketProvider::BindPrinter](../prcomoem/nf-prcomoem-iprintoemprintticketprovider-bindprinter.md) method. This method should then read all of the settings that it supported from the print ticket, and place those settings into the DEVMODEW structure. Note that not all of the features necessarily will be represented, and that often Option instances that are present might not contain all of the Scored Property instances that the provider would normally populate. If the provider makes any changes to the settings that were populated by the system during conversion from print ticket to DEVMODEW, the provider should perform the reverse of that change in this method. After the provider returns, the system then overwrites any public DEVMODEW settings that are represented in the print ticket but that are not explicitly disabled by the provider.

## -see-also

[IPrintOemPrintTicketProvider](../prcomoem/nn-prcomoem-iprintoemprintticketprovider.md)

[IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket](../prcomoem/nf-prcomoem-iprintoemprintticketprovider-convertdevmodetoprintticket.md)
