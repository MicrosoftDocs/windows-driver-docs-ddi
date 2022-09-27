---
UID: NF:prdrvcom.IPrintTicketProvider.BindPrinter
tech.root: print
title: IPrintTicketProvider::BindPrinter (prdrvcom.h)
ms.date: 08/26/2022
targetos: Windows
description: The IPrintTicketProvider::BindPrinter method binds a printer or print queue to a specific version of the print ticket schema, which enables the core driver to associate a set of private namespace uniform resource identifiers (URIs) with a device.
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
 - IPrintTicketProvider::BindPrinter
f1_keywords:
 - IPrintTicketProvider::BindPrinter
 - prdrvcom/IPrintTicketProvider::BindPrinter
dev_langs:
 - c++
helpviewer_keywords:
 - BindPrinter
---

## -description

The **IPrintTicketProvider::BindPrinter** method binds a printer or print queue to a specific version of the print ticket schema, which enables the core driver to associate a set of private namespace uniform resource identifiers (URIs) with a device.

## -parameters

### -param hPrinter [in]

The spooler's print handle, which is supplied by the core driver. The provider should not close this handle at any time because the client of the provider is responsible for managing the lifetime of this handle. The provider can cache the print handle; all future calls are relative to the printer that is associated with this handle.

### -param version [in]

The major version number of the print ticket or print ticket schema that the print ticket manager requests the OEM plug-in provider to support. Windows Vista supports only version 1. The provider should fail any attempt to bind to a version that it does not support or recognize.

### -param pOptions [out]

A pointer to a variable that receives one of the following enumerated values:

- PTSHIM_DEFAULT

    The system places a binary encoding (a BLOB - binary large object) of the private portion of the **DEVMODEW** structure into the print ticket in a conversion of a **DEVMODEW** to a print ticket.

- PTSHIM_NOSNAPSHOT

    The system will not place a binary encoding (a BLOB) of the private portion of the **DEVMODEW** structure into the print ticket in a conversion of a **DEVMODEW** to a print ticket. Use this value if all of the public and private **DEVMODEW** members are fully represented in the print ticket.

### -param pDevModeFlags [out]

A pointer to a DWORD-typed variable that receives a set of bit flags that indicate which public **DEVMODEW** members should not be processed by the print ticket shim in DEVMODEW-to-print ticket or print ticket-to-DEVMODEW conversions. A bit flag that is present in this parameter indicates either that the printer does not support the associated DEVMODEW member or that the provider handles that DEVMODEW characteristic. For example, if DM_MEDIATYPE is set in *pDevModeFlags, either the printer does not support multiple media types, or the provider is responsible for supporting multiple media types. (All of the DM_XXX bit flags are defined in wingdi.h and described in the Microsoft Windows SDK.) By default, the print ticket shim handles all of the members that are represented in the **dmFlags** member of the default **DEVMODEW** structure.

### -param cNamespaces [out]

A pointer to a variable that receives the number of private namespace URIs that are used in the plug-in. This number represents the count of strings in the array that is pointed to by *ppNamespaces*.

### -param ppNamespaces [out]

A pointer to a variable that receives the address of the first element of a BSTR array. The plug-in fills each array position with a namespace URI. For more information about this parameter, see the following Remarks section.

## -returns

**IPrintTicketProvider::BindPrinter** should return one of the following values:

| Return code | Description |
|--|--|
| **S_OK** | The operation succeeded. |
| **E_VERSION_NOT_SUPPORTED** | The plug-in does not support the version of the print schema that is specified in the *version* parameter. |

## -remarks

Binding to a device enables the provider to cache certain objects and handles that it will need for future print ticket or device capabilities services on that device. For example, the printer handle in the hPrinter parameter can be cached. The IPrintTicketProvider::BindPrinter method is guaranteed to be called only once.

The driver is responsible for allocating memory for the array that is pointed to by the ppNamespaces parameter and for the namespace URI strings. The array should be allocated by using the **CoTaskMemAlloc** function; the namespace strings should be allocated by using the **SysAllocString** function. Both functions are described in the Windows SDK documentation. The array that is pointed to by the ppNamespaces parameter is not required to contain the namespaces for the Print Schema Keywords or the Print Schema Framework.

An **IPrintTicketProvider** object does not have to be able to bind more than once. The print ticket manager always uses different **IPrintTicketProvider** object instances for binding to different devices. All resources that are acquired in a successful call to **IPrintTicketProvider::BindPrinter** should be released when the reference count of an **IPrintTicketProvider** object is zero. Note that the provider should not close the handle that was passed into the call to **BindPrinter**. The print ticket manager might create multiple providers for the same device, in different versions, if multiple versions are supported.

## -see-also

[IPrintTicketProvider](./nn-prdrvcom-iprintticketprovider.md)

[IPrintTicketProvider::ConvertDevModeToPrintTicket](./nf-prdrvcom-iprintticketprovider-convertdevmodetoprintticket.md)

[IPrintTicketProvider::ConvertPrintTicketToDevMode](./nf-prdrvcom-iprintticketprovider-convertprinttickettodevmode.md)

[IPrintTicketProvider::GetSupportedVersions](./nf-prdrvcom-iprintticketprovider-getsupportedversions.md)
