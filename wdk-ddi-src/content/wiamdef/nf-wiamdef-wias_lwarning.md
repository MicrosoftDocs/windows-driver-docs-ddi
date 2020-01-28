---
UID: NF:wiamdef.WIAS_LWARNING
title: WIAS_LWARNING macro (wiamdef.h)
description: The WIAS_LWARNING macro is obsolete for Windows Vista. The WIAS_LWARNING macro writes a diagnostic WIA_WARNING message to the log file.
old-location: image\wias_lwarning.htm
tech.root: image
ms.assetid: 2959c470-1da7-4396-a591-7a356379f9de
ms.date: 05/03/2018
ms.keywords: IWiaLog_bac21803-be4c-4ce0-a241-b9380cb627ab.xml, WIAS_LWARNING, WIAS_LWARNING macro [Imaging Devices], image.wias_lwarning, wiamdef/WIAS_LWARNING
f1_keywords:
 - "wiamdef/WIAS_LWARNING"
req.header: wiamdef.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Obsolete, do not use.
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
- WIAS_LWARNING
product:
- Windows
targetos: Windows
req.typenames: 
---

# WIAS_LWARNING macro

## -description

The WIAS_LWARNING macro is obsolete. Do not use.

The WIAS_LWARNING macro writes a diagnostic WIA_WARNING message to the log file.

## -parameters

### -param pILog

### -param ResID

### -param Args

- **format_string, ...** - Specifies a variable argument list, which starts with an ANSI format string that describes the message and any format identifiers. The ellipsis (...) specifies a variable number of arguments that need to be output. The error text should be prefixed with the full name of the method or function and generate the message in the format of "class::method, error-text".

- **lResId** - Specifies the resource ID. This value should be set to WIALOG_NO_RESOURCE_ID.

- **pIWiaLog** - Pointer to an [IWiaLog Interface](https://docs.microsoft.com/windows-hardware/drivers/ddi/wia_lh/nn-wia_lh-iwialog).

## -remarks

The following is an example of how the macro can be used:

```cppWIAS_LWARNING(g_pIWiaLog, WIALOG_NO_RESOURCE_ID, ("MyClass::MyMethod, This is my text and my lValue = %d", lValue));
```

Please note that it does not write to the new log file used in modern Windows operating systems.

## -see-also

[WIAS_LERROR](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wias_lerror)

[WIAS_LHRESULT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wias_lhresult)

[WIAS_LTRACE](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wias_ltrace)
