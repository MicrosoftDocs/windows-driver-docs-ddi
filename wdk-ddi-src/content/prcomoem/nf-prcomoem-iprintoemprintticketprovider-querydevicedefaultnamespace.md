---
UID: NF:prcomoem.IPrintOemPrintTicketProvider.QueryDeviceDefaultNamespace
title: IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace (prcomoem.h)
description: The IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace method queries the device for its default namespace uniform resource identifier (URI).
tech.root: print
ms.date: 08/22/2022
keywords: ["IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace"]
ms.keywords: IPrintOemPrintTicketProvider interface [Print Devices],QueryDeviceDefaultNamespace method, IPrintOemPrintTicketProvider.QueryDeviceDefaultNamespace, IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace, QueryDeviceDefaultNamespace, QueryDeviceDefaultNamespace method [Print Devices], QueryDeviceDefaultNamespace method [Print Devices],IPrintOemPrintTicketProvider interface, prcomoem/IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace, print.iprintoemprintticketprovider_querydevicedefaultnamespace, print_ticket-package_9b7bc4a4-a8db-4bef-b592-b6774c8d9fb2.xml
req.header: prcomoem.h
req.include-header: Prcomoem.h
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
 - IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace
 - prcomoem/IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace
---

## -description

The **IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace** method queries the device for its default namespace uniform resource identifier (URI).

## -parameters

### -param pbstrNamespaceUri [out]

A pointer to a BSTR that receives the namespace URI. The plug-in places the namespace URI in the buffer that is pointed to by *pbstrNamespaceUri*. **IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace** is responsible for allocating the string by means of a call to **SysAllocString** (described in the Microsoft Windows SDK documentation), but the caller is responsible for freeing the string.

## -returns

**IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace** should return one of the following values.

| Return code | Description |
|--|--|
| **S_OK** | The operation succeeded. |
| **E_NOTIMPL** | The plug-in does not intend to override the default namespace that the core driver generated from the plug-in's provider. |

## -remarks

The plug-in should specify the name of the private namespace URI that the core driver should use to handle any features that are defined in the GPD file or PPD file that the core driver does not recognize. The plug-in might specify a set of namespaces as a result of the call to the [IPrintOemPrintTicketProvider::BindPrinter](./nf-prcomoem-iprintoemprintticketprovider-bindprinter.md) method. The purpose of the **IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace** is to inform the core driver about which of these namespaces is to be used as the default namespace. The core driver associates all of the features that it does not recognize with this default namespace, and places any such features in the print ticket.

> [!NOTE]
> When **IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace** returns, the core driver is responsible for adding the private namespace URI that the plug-in has specified (in **pbstrNamespaceUri*) to the root node of the DOM document. The core driver also must define a prefix for the private namespace that the plug-in should use when the plug-in adds a new node to the print ticket under the plug-in's private namespace. The plug-in should not define its own prefix for this default private namespace URI.

## -see-also

[IPrintOemPrintTicketProvider](/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintoemprintticketprovider)

[IPrintOemPrintTicketProvider::BindPrinter](./nf-prcomoem-iprintoemprintticketprovider-bindprinter.md)
