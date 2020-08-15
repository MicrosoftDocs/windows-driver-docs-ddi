---
UID: NF:wiamdef.wiasCreateLogInstance
title: wiasCreateLogInstance function (wiamdef.h)
description: The wiasCreateLogInstance function creates an instance of a logging object.
old-location: image\wiascreateloginstance.htm
tech.root: image
ms.assetid: 7a340187-51c5-4997-b4d0-5b89ea8e16c0
ms.date: 05/03/2018
keywords: ["wiasCreateLogInstance function"]
ms.keywords: image.wiascreateloginstance, wiamdef/wiasCreateLogInstance, wiasCreateLogInstance, wiasCreateLogInstance function [Imaging Devices], wiasFncs_f3d782d2-d11c-41bb-9d1e-d2619547dfda.xml
f1_keywords:
 - "wiamdef/wiasCreateLogInstance"
 - "wiasCreateLogInstance"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Wiaservc.dll
api_name:
- wiasCreateLogInstance
targetos: Windows
req.typenames: 
---

# wiasCreateLogInstance function

## -description

The **wiasCreateLogInstance** function creates an instance of a logging object.

## -parameters

### -param pModuleHandle 
[in]
Pointer to the module handle, which is used to filter output.

### -param ppIWiaLogEx 
[out]
Pointer to a memory location that receives the address of the logging interface.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the [WIA error codes](https://docs.microsoft.com/windows/win32/wia/-wia-error-codes).
