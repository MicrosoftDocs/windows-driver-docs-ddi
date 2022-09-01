---
UID: NF:prdrvcom.IPrintTicketProvider.ConvertPrintTicketToDevMode
tech.root: print
title: IPrintTicketProvider::ConvertPrintTicketToDevMode (prdrvcom.h)
ms.date: 08/29/2022
targetos: Windows
description: The IPrintTicketProvider::ConvertPrintTicketToDevMode method converts a print ticket to a DEVMODEW structure.
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
 - IPrintTicketProvider::ConvertPrintTicketToDevMode
f1_keywords:
 - IPrintTicketProvider::ConvertPrintTicketToDevMode
 - prdrvcom/IPrintTicketProvider::ConvertPrintTicketToDevMode
dev_langs:
 - c++
helpviewer_keywords:
 - ConvertPrintTicketToDevMode
---

## -description

The **IPrintTicketProvider::ConvertPrintTicketToDevMode** method converts a print ticket to a ****DEVMODEW**** structure.

## -parameters

### -param pPrintTicket [in]

A pointer to the input print ticket. **IPrintTicketProvider::ConvertPrintTicketToDevMode** converts the settings in the input print ticket into fields in the **DEVMODEW** structure.

### -param cbDevmodeIn [in]

The size, in bytes, of the input **DEVMODEW** structure. This size includes both the public and private sections of the **DEVMODEW** structure.

### -param pDevmodeIn [in]

A pointer to the input **DEVMODEW** structure, which contains default settings. The **DEVMODEW** structure can be the print queue default **DEVMODEW** structure, or it can be the user default **DEVMODEW** structure. Because this parameter can represent the user default **DEVMODEW** structure, the OEM plug-in provider must validate the data in that structure. A user default **DEVMODEW** structure might not be valid for a specific driver, for example, when the print queue's driver changes or is upgraded.

### -param pcbDevmodeOut [out]

A pointer to a variable that contains the size, in bytes, of the output **DEVMODEW** structure.

### -param ppDevmodeOut [out]

A pointer to a variable that contains the address of the output **DEVMODEW** structure. When **IPrintTicketProvider::ConvertPrintTicketToDevMode** successfully returns, the members of the output **DEVMODEW** structure will be reset to reflect the settings in the print ticket. For more information, see the following Remarks section.

## -returns

**IPrintTicketProvider::ConvertPrintTicketToDevMode** should return **S_OK** if the operation succeeds. Otherwise, this method should return a standard COM error code.

## -remarks

The core driver calls the **IPrintTicketProvider::ConvertPrintTicketToDevMode** method before it performs its part of the conversion of a print ticket to a **DEVMODEW** structure. In the call to this method, the core driver passes an input print ticket that is fully populated and a **DEVMODEW** structure that is set to default values. In the conversion, the plug-in must undo any changes that it made to the print ticket during the previous conversion from a **DEVMODEW** structure to a print ticket. If, during this previous conversion, the plug-in moved a feature from a private namespace to the public namespace, the plug-in must restore the feature to the private namespace in a format that is suitable for the core driver, that is, to the format in which the core driver had previously placed the feature in the print ticket that was provided to the plug-in in the **IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket** method. This restoration is necessary so that the core driver can recognize a feature in the print ticket and reflect its settings in the private portion of the core driver's **DEVMODEW** structure while the core driver performs its part of the print ticket-to-**DEVMODEW** conversion.

Before the system converts a print ticket back to a **DEVMODEW** structure, it first loads the default **DEVMODEW**. The system then calls the provider's **IPrintTicketProvider::BindPrinter** method. This method should then read all of the settings that it supported from the print ticket, and place those settings into the **DEVMODEW** structure. Note that not all of the features necessarily will be represented, and that often Option instances that are present might not contain all of the Scored Property instances that the provider would normally populate. If the provider makes any changes to the settings that were populated by the system during conversion from print ticket to **DEVMODEW**, the provider should perform the reverse of that change in this method. After the provider returns, the system then overwrites any public **DEVMODEW** settings that are represented in the print ticket but that are not explicitly disabled by the provider.

## -see-also

[IPrintTicketProvider](./nn-prdrvcom-iprintticketprovider.md)

[IPrintTicketProvider::ConvertDevModeToPrintTicket](./nf-prdrvcom-iprintticketprovider-convertdevmodetoprintticket.md)
