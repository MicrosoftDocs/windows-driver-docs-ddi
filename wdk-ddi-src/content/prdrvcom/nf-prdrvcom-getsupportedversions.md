---
UID: NF:prdrvcom.GetSupportedVersions
title: GetSupportedVersions function (prdrvcom.h)
description: The IPrintOemPrintTicketProvider::GetSupportedVersions method retrieves major version numbers of the print schemas that are supported by the plug-in provider.
tech.root: print
ms.date: 08/22/2022
keywords: ["GetSupportedVersions function"]
ms.keywords: GetSupportedVersions, GetSupportedVersions method [Print Devices], GetSupportedVersions method [Print Devices],IPrintOemPrintTicketProvider interface, IPrintOemPrintTicketProvider interface [Print Devices],GetSupportedVersions method, IPrintOemPrintTicketProvider::GetSupportedVersions, prdrvcom/IPrintOemPrintTicketProvider::GetSupportedVersions, print.IPrintOemPrintTicketProvider_getsupportedversions, print_ticket-package_3c9ed7b7-a38f-49b2-a7fc-7fc78aa39a27.xml
f1_keywords:
 - "prdrvcom/IPrintOemPrintTicketProvider.GetSupportedVersions"
 - "IPrintOemPrintTicketProvider.GetSupportedVersions"
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
- Prdrvcom.h
api_name:
- IPrintOemPrintTicketProvider.GetSupportedVersions
targetos: Windows
req.typenames: 
---

## -description

The **IPrintOemPrintTicketProvider::GetSupportedVersions** method retrieves major version numbers of the print schemas that are supported by the plug-in provider.

## -parameters

### -param hPrinter [in]

A handle to the print device.

### -param ppVersions [out]

A pointer to a variable that receives the address of the first element of an array of version numbers. Version numbers in the array can appear in any order. For more information about this parameter, see the following Remarks section.

### -param cVersions [out]

A pointer to a variable that receives the number of elements in the array that is pointed to by **ppVersions*.

## -returns

**IPrintOemPrintTicketProvider::GetSupportedVersions** should return S_OK if the operation succeeds. If this method fails because of lack of memory or other resources, it should return a standard COM error code.

## -remarks

**IPrintOemPrintTicketProvider::GetSupportedVersions** returns the major version numbers of the print schemas that are supported by the provider interface. (The only currently defined version number is 1.) Providers can omit intermediate versions

The plug-in is responsible for allocating the array memory that is pointed to by the *ppVersions* parameter. The plug-in should allocate this memory by using the **CoTaskMemAlloc** function (described in the Microsoft Windows SDK documentation), but the plug-in is not responsible for freeing this memory.

Because **IPrintOemPrintTicketProvider::GetSupportedVersions** can be called before the [IPrintOemPrintTicketProvider::BindPrinter](../prcomoem/nf-prcomoem-iprintoemprintticketprovider-bindprinter.md) method is called, the OEM plug-in provider must check version support based on the handle that is passed in the *hPrinter* parameter. As a result, the OEM plug-in provider should not close the printer handle that is associated with *hPrinter*.

## -see-also

[IPrintOemPrintTicketProvider](../prcomoem/nn-prcomoem-iprintoemprintticketprovider.md)

[IPrintOemPrintTicketProvider::BindPrinter](../prcomoem/nf-prcomoem-iprintoemprintticketprovider-bindprinter.md)
