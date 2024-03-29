---
UID: NF:wiamdef.wiasReadMultiple
title: wiasReadMultiple function (wiamdef.h)
description: The wiasReadMultiple function retrieves multiple property values from a WIA item.
old-location: image\wiasreadmultiple.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["wiasReadMultiple function"]
ms.keywords: image.wiasreadmultiple, wiamdef/wiasReadMultiple, wiasFncs_c6d42143-4cd8-4f9a-bbf4-aec0ce2c0615.xml, wiasReadMultiple, wiasReadMultiple function [Imaging Devices]
req.header: wiamdef.h
req.include-header: Wiamdef.h
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
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - wiasReadMultiple
 - wiamdef/wiasReadMultiple
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasReadMultiple
---

# wiasReadMultiple function


## -description

The **wiasReadMultiple** function retrieves multiple property values from a WIA item.

## -parameters

### -param pWiasContext [in]


Pointer to a WIA item context.

### -param ulCount

Specifies the number of properties to read.

### -param ps [in]


Pointer to the first element of an array of [PROPSPEC](/windows/win32/api/propidl/ns-propidl-propspec) structures, containing the properties to read.

### -param pv [out]


Pointer to the first element of an array of [PROPVARIANT](/windows/win32/api/propidl/ns-propidl-propvariant) structures. Upon return, these structures contain new values for the properties.

### -param pvOld [out, optional]


Pointer to the first element of an array of PROPVARIANT structures previously allocated by the minidriver. Upon return, the array contains the previous values of the property data. If this information is not needed, this parameter can be set to **NULL**.

## -returns

On success, the function returns S_OK.

If the function fails, it returns a standard COM error or one of the [WIA error codes](/windows/win32/wia/-wia-error-codes).

## -remarks

This function reads multiple properties from a WIA item. When the call succeeds, the minidriver must call [**PropVariantClear**](/windows/win32/api/combaseapi/nf-combaseapi-propvariantclear) on each element in the array specified by the *pv* parameter. See [**IPropertyStorage::ReadMultiple**](/windows/win32/api/propidl/nf-propidl-ipropertystorage-readmultiple) for more information.

## -see-also

[wiasWriteMultiple](./nf-wiamdef-wiaswritemultiple.md)
