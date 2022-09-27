---
UID: NF:prcomoem.IPrintOemPrintTicketProvider.GetSupportedVersions
title: IPrintOemPrintTicketProvider::GetSupportedVersions (prcomoem.h)
description: The IPrintOemPrintTicketProvider::GetSupportedVersions method retrieves major versions of the print schemas that are supported by the plug-in provider.
tech.root: print
ms.date: 08/22/2022
keywords: ["IPrintOemPrintTicketProvider::GetSupportedVersions"]
ms.keywords: GetSupportedVersions, GetSupportedVersions method [Print Devices], GetSupportedVersions method [Print Devices],IPrintOemPrintTicketProvider interface, IPrintOemPrintTicketProvider interface [Print Devices],GetSupportedVersions method, IPrintOemPrintTicketProvider.GetSupportedVersions, IPrintOemPrintTicketProvider::GetSupportedVersions, prcomoem/IPrintOemPrintTicketProvider::GetSupportedVersions, print.iprintoemprintticketprovider_getsupportedversions, print_ticket-package_f20858fb-a11d-45b4-a8db-6a492b761cfc.xml
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
 - IPrintOemPrintTicketProvider::GetSupportedVersions
 - prcomoem/IPrintOemPrintTicketProvider::GetSupportedVersions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Prcomoem.h
api_name:
 - IPrintOemPrintTicketProvider::GetSupportedVersions
---

## -description

The **IPrintOemPrintTicketProvider::GetSupportedVersions** method retrieves major versions of the print schemas that are supported by the plug-in provider.

## -parameters

### -param hPrinter [in]

A handle to the print device.

### -param ppVersions [out]

A pointer to a variable that receives the address of the first element of an array of version numbers. Version numbers in the array can appear in any order. For more information about this parameter, see the following Remarks section.

### -param cVersions [out]

A pointer to a variable that receives the number of elements in the array that is pointed to by **ppVersions*.

## -returns

**IPrintOemPrintTicketProvider::GetSupportedVersions** should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.

## -remarks

**IPrintOemPrintTicketProvider::GetSupportedVersions** returns the major version numbers of the print schemas that are supported by the provider interface. (The only currently defined version number is 1.) Providers can omit intermediate versions.

The plug-in is responsible for allocating the array memory that is pointed to by the *ppVersions* parameter. The plug-in should allocate this memory by using the **CoTaskMemAlloc** function (described in the Microsoft Windows SDK documentation), but it is not responsible for freeing this memory.

**IPrintOemPrintTicketProvider::GetSupportedVersions** can be called before the [IPrintOemPrintTicketProvider::BindPrinter](./nf-prcomoem-iprintoemprintticketprovider-bindprinter.md) method is called. As a result, the OEM plug-in provider should not close the printer handle that is associated with the *hPrinter* parameter.

## -see-also

[IPrintOemPrintTicketProvider](./nn-prcomoem-iprintoemprintticketprovider.md)

[IPrintOemPrintTicketProvider::BindPrinter](./nf-prcomoem-iprintoemprintticketprovider-bindprinter.md)
