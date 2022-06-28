---
UID: NF:wiautil.wiauRegGetDwordA
title: wiauRegGetDwordA function (wiautil.h)
description: The wiauRegGetDword function gets a DWORD value from the DeviceData section of the registry.
tech.root: image
ms.date: 04/20/2022
keywords: ["wiauRegGetDwordA function"]
ms.keywords: image.wiaureggetdword, wiauFncs_a58ebb21-21ce-4815-9dd6-5a1906412a2f.xml, wiauRegGetDword, wiauRegGetDword function [Imaging Devices], wiauRegGetDwordA, wiauRegGetDwordW, wiautil/wiauRegGetDword
req.header: wiautil.h
req.include-header: Wiautil.h
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
 - wiauRegGetDwordA
 - wiautil/wiauRegGetDwordA
 - wiauRegGetDword
 - wiautil/wiauRegGetDword
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wiautil.h
api_name:
 - wiauRegGetDwordA
 - wiauRegGetDword
---

## -description

The **wiauRegGetDword** function gets a **DWORD** value from the **DeviceData** section of the registry.

## -parameters

### -param hkKey [in]

Specifies the registry key handle. This parameter should be set to the value pointed to by the *phkeyDeviceData*parameter when [wiauRegOpenData](./nf-wiautil-wiauregopendataw.md) returns.

### -param pszValueName [in]

Points to the first byte of a Unicode string containing the name of the registry entry.

### -param pdwValue [out]

Pointer to a memory location that receives the returned DWORD value.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error.

## -see-also

[wiauRegGetStr](./nf-wiautil-wiaureggetstrw.md)

[wiauRegOpenData](./nf-wiautil-wiauregopendataw.md)