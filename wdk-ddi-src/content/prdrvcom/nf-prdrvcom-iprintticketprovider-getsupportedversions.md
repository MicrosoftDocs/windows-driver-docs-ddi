---
UID: NF:prdrvcom.IPrintTicketProvider.GetSupportedVersions
tech.root: print
title: IPrintTicketProvider::GetSupportedVersions (prdrvcom.h)
ms.date: 08/31/2022
targetos: Windows
description: The IPrintTicketProvider::GetSupportedVersions method retrieves major version numbers of the print schemas that are supported by the plug-in provider.
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
 - IPrintTicketProvider::GetSupportedVersions
f1_keywords:
 - IPrintTicketProvider::GetSupportedVersions
 - prdrvcom/IPrintTicketProvider::GetSupportedVersions
dev_langs:
 - c++
helpviewer_keywords:
 - GetSupportedVersions
---

## -description

The **IPrintTicketProvider::GetSupportedVersions** method retrieves major version numbers of the print schemas that are supported by the plug-in provider.

## -parameters

### -param hPrinter [in]

A handle to the print device.

### -param ppVersions [out]

A pointer to a variable that receives the address of the first element of an array of version numbers. Version numbers in the array can appear in any order. For more information about this parameter, see the following Remarks section.

### -param cVersions [out]

A pointer to a variable that receives the number of elements in the array that is pointed to by *ppVersions*.

## -returns

**IPrintTicketProvider::GetSupportedVersions** should return **S_OK** if the operation succeeds. If this method fails because of lack of memory or other resources, it should return a standard COM error code.

## -remarks

**IPrintTicketProvider::GetSupportedVersions** returns the major version numbers of the print schemas that are supported by the provider interface. The only currently defined version number is 1. Providers can omit intermediate versions.

The plug-in is responsible for allocating the array memory that is pointed to by the *ppVersions* parameter. The plug-in should allocate this memory by using the **CoTaskMemAlloc** function described in the Microsoft Windows SDK documentation, but the plug-in is not responsible for freeing this memory.

Because **IPrintTicketProvider::GetSupportedVersions** can be called before the **IPrintTicketProvider::BindPrinter** method is called, the OEM plug-in provider must check version support based on the handle that is passed in the *hPrinter* parameter. As a result, the OEM plug-in provider should not close the printer handle that is associated with *hPrinter*.

## -see-also

[IPrintTicketProvider](./nn-prdrvcom-iprintticketprovider.md)

[IPrintTicketProvider::BindPrinter](./nf-prdrvcom-iprintticketprovider-bindprinter.md)
