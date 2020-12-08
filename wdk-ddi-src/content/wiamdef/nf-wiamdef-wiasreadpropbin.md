---
UID: NF:wiamdef.wiasReadPropBin
title: wiasReadPropBin function (wiamdef.h)
description: The wiasReadPropBin function retrieves a binary-data property value from a WIA item.
old-location: image\wiasreadpropbin.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["wiasReadPropBin function"]
ms.keywords: image.wiasreadpropbin, wiamdef/wiasReadPropBin, wiasFncs_484baa0a-a423-4f4d-a33c-d155a8f4974c.xml, wiasReadPropBin, wiasReadPropBin function [Imaging Devices]
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
 - wiasReadPropBin
 - wiamdef/wiasReadPropBin
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wiaservc.dll
api_name:
 - wiasReadPropBin
---

# wiasReadPropBin function


## -description

The **wiasReadPropBin** function retrieves a binary-data property value from a WIA item.

## -parameters

### -param pWiasContext 

[in]
Pointer to a WIA item context.

### -param propid

Specifies the property identifier.

### -param ppbVal 

[out]
Pointer to a memory location that receives the address of a buffer allocated by this function. Upon return, the buffer contains the property's binary data.

### -param ppbValOld 

[out, optional]
Pointer to a memory location that receives the address of a buffer allocated by the minidriver. Upon return, the buffer contains the previous value of the property's binary data. If this information is not needed, this parameter can be set to **NULL**.

### -param bMustExist

Indicates whether the property must exist. If set to **TRUE**, the property must exist; if set to **FALSE**, the property does not have to exist.

## -returns

On success, the function returns S_OK.

If the function fails, it returns a standard COM error or one of the [WIA error codes](/windows/win32/wia/-wia-error-codes).

## -remarks

This function allocates a buffer and stores its address in the *ppbVal* parameter. The minidriver must free the buffer by calling [**CoTaskMemFree**](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree).

## -see-also

[wiasReadPropFloat](./nf-wiamdef-wiasreadpropfloat.md)

[wiasReadPropGuid](./nf-wiamdef-wiasreadpropguid.md)

[wiasReadPropLong](./nf-wiamdef-wiasreadproplong.md)

[wiasReadPropStr](./nf-wiamdef-wiasreadpropstr.md)

[wiasWritePropBin](./nf-wiamdef-wiaswritepropbin.md)
