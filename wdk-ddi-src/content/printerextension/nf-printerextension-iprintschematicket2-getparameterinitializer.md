---
UID: NF:printerextension.IPrintSchemaTicket2.GetParameterInitializer
title: IPrintSchemaTicket2::GetParameterInitializer (printerextension.h)
description: The GetParameterInitializer method retrieves the IPrintSchemaParameterInitializer object, and it represents the psf:ParameterInit element in the PrintTicket XML.
old-location: print\iprintschematicket2_getparameterinitializer.htm
tech.root: print
ms.assetid: E5403359-A757-4530-B17B-C80E8A45AA92
ms.date: 06/25/2020
keywords: ["IPrintSchemaTicket2::GetParameterInitializer"]
ms.keywords: GetParameterInitializer, GetParameterInitializer method [Print Devices], GetParameterInitializer method [Print Devices],IPrintSchematicket2 interface, IPrintSchemaTicket2.GetParameterInitializer, IPrintSchemaTicket2::GetParameterInitializer, IPrintSchematicket2 interface [Print Devices],GetParameterInitializer method, IPrintSchematicket2::GetParameterInitializer, print.iprintschematicket2_getparameterinitializer, printerextension/IPrintSchematicket2::GetParameterInitializer
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
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
 - IPrintSchemaTicket2::GetParameterInitializer
 - printerextension/IPrintSchemaTicket2::GetParameterInitializer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchematicket2.GetParameterInitializer
---

# IPrintSchemaTicket2::GetParameterInitializer


## -description

The **GetParameterInitializer** method retrieves the [IPrintSchemaParameterInitializer](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaparameterinitializer) object, and it  represents the \<psf:ParameterInit\> element in the PrintTicket XML.

The keyword name and keyword namespace URI specify the **IPrintSchemaParameterInitializer** object to be retrieved.

## -parameters

### -param bstrName 

[in]
The keyword name.

### -param bstrNamespaceUri 

[in]
The keyword namespace URI.

### -param ppParameterInitializer 

[out, retval]
The [IPrintSchemaParameterInitializer](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaparameterinitializer) object.

## -returns

The **GetParameterInitializer** method returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintSchemaParameterInitializer](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaparameterinitializer)

[IPrintSchematicket2](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket2)

