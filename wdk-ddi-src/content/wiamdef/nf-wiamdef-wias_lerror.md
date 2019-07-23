---
UID: NF:wiamdef.WIAS_LERROR
title: WIAS_LERROR macro (wiamdef.h)
description: The WIAS_LERROR macro is obsolete. It is recommended that the WIAS_ERROR macro be used instead.The WIAS_LERROR macro writes a diagnostic WIA_ERROR message to the log file.
old-location: image\wias_lerror.htm
tech.root: image
ms.assetid: 71949653-08c7-4f22-951d-6e1595b10700
ms.date: 05/03/2018
ms.keywords: IWiaLog_b765e146-4e57-447c-9e9d-0f3cdc784291.xml, WIAS_LERROR, WIAS_LERROR macro [Imaging Devices], image.wias_lerror, wiamdef/WIAS_LERROR
ms.topic: macro
f1_keywords:
 - "wiamdef/WIAS_LERROR"
req.header: wiamdef.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Obsolete, use WIAS_ERROR instead.
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
- HeaderDef
api_location:
- wiamdef.h
api_name:
- WIAS_LERROR
product:
- Windows
targetos: Windows
req.typenames: 
---

# WIAS_LERROR macro

## -description

The WIAS_LERROR macro is obsolete. It is recommended that the [WIAS_ERROR](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_error) macro be used instead.

The WIAS_LERROR macro writes a diagnostic WIA_ERROR message to the log file.

## -parameters

### -param pILog

### -param ResID

### -param Args

- **format_string, ...** - Specifies a variable argument list, which starts with an ANSI format string that describes the message and any format identifiers. The ellipsis (...) specifies a variable number of arguments that need to be output. The error text should be prefixed with the full name of the method or function and generate the message in the format of "class::method, error-text".

- **lResId** - Specifies the resource ID. This value should be set to WIALOG_NO_RESOURCE_ID.

- **pIWiaLog** - Pointer to an [IWiaLog Interface](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wia_lh/nn-wia_lh-iwialog).

## -remarks

The following is an example of how the macro can be used:

```cpp
WIAS_LERROR(g_pIWiaLog, WIALOG_NO_RESOURCE_ID, ("MyClass::MyMethod, This is my text and my lValue = %d", lValue));
```

The WIAS_LERROR macro is obsolete and not recommended for use because it does not record its output to the *Wiatrace.log* diagnostic log file. It is recommended that the [WIAS_ERROR](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_error) macro be used instead.

## -see-also

[WIAS_ERROR](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_error)

[WIAS_LHRESULT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_lhresult)

[WIAS_LTRACE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_ltrace)

[WIAS_LWARNING](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_lwarning)
