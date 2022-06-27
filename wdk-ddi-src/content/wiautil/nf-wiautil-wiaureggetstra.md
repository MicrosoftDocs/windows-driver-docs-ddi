---
UID: NF:wiautil.wiauRegGetStrA
title: wiauRegGetStrA function (wiautil.h)
description: The wiauRegGetStr function gets a string value from the DeviceData section of the registry.
tech.root: image
ms.date: 04/20/2022
keywords: ["wiauRegGetStrA function"]
ms.keywords: image.wiaureggetstr, wiauFncs_b9145502-734d-40de-8086-c1f193966269.xml, wiauRegGetStr, wiauRegGetStr function [Imaging Devices], wiauRegGetStrA, wiauRegGetStrW, wiautil/wiauRegGetStr
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
 - wiauRegGetStrA
 - wiautil/wiauRegGetStrA
 - wiauRegGetStr
 - wiautil/wiauRegGetStr
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wiautil.h
api_name:
 - wiauRegGetStrA
 - wiauRegGetStr
---

## -description

The **wiauRegGetStr** function gets a string value from the **DeviceData** section of the registry.

## -parameters

### -param hkKey [in]

Specifies the registry key handle. This parameter should be set to the value pointed to by the *phkeyDeviceData* parameter when [wiauRegOpenData](/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiauregopendataw) returns.

### -param pszValueName [in]

Points to the first character of a Unicode string containing the name of the registry entry.

### -param pszValue [out]

Pointer to a memory location that receives the string value, including a terminating null character.

### -param pdwLength [in, out]

Pointer to a memory location that receives the length, in bytes, of the string value pointed to by the *pwszValue* parameter. The length includes the terminating null character.

## -returns

On success, the function returns S_OK. If the function fails, it returns a standard COM error.

## -see-also

[wiauRegGetDword](/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiaureggetdwordw)

[wiauRegOpenData](/windows-hardware/drivers/ddi/wiautil/nf-wiautil-wiauregopendataw)
