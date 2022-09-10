---
UID: NF:prdrvcom.IPrintTicketProvider2.GetPrintCapabilities
tech.root: print
title: IPrintTicketProvider2::GetPrintCapabilities (prdrvcom.h)
ms.date: 08/29/2022
targetos: Windows
description: The IPrintTicketProvider2::GetPrintCapabilities method queries the provider for a complete print capabilities document that describes the printer's features and parameters.
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
 - IPrintTicketProvider2::GetPrintCapabilities
f1_keywords:
 - IPrintTicketProvider2::GetPrintCapabilities
 - prdrvcom/IPrintTicketProvider2::GetPrintCapabilities
dev_langs:
 - c++
helpviewer_keywords:
 - GetPrintCapabilities
---

## -description

The **IPrintTicketProvider2::GetPrintCapabilities** method queries the provider for a complete print capabilities document that describes the printer's features and parameters.

## -parameters

### -param pPrintTicket [in]

A pointer to the print ticket. The settings of the print ticket constrain the device capabilities.

### -param ppCapabilities [out]

A pointer to a variable that receives the address of the device capabilities document.

## -returns

**IPrintTicketProvider2::GetPrintCapabilities** should return **S_OK** if the operation succeeds. Otherwise, this method should return a standard COM error code.

## -remarks

The input print ticket should be used to determine and describe constraints on the settings in the output print capabilities document. No features, options, and parameters that are described in the output print capabilities document should change because of the contents of the input print ticket. Only the constraint status of the features, options, and parameters are subject to change.

## -see-also
