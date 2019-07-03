---
UID: NF:wiamdef.WIAS_LTRACE
title: WIAS_LTRACE macro (wiamdef.h)
description: The WIAS_LTRACE macro is obsolete for Windows Vista and later. It is recommended that the WIAS_TRACE macro be used instead.The WIAS_LTRACE macro writes a diagnostic WIA_TRACE message to the log file.
old-location: image\wias_ltrace.htm
tech.root: image
ms.assetid: 513fd718-3d35-4a7b-be28-b002a8108e86
ms.date: 05/03/2018
ms.keywords: IWiaLog_bb7ae826-5b43-47c1-bf94-bd491d8b91a7.xml, WIAS_LTRACE, WIAS_LTRACE macro [Imaging Devices], image.wias_ltrace, wiamdef/WIAS_LTRACE
ms.topic: macro
req.header: wiamdef.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Obsolete, use WIAS_TRACE instead.
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
- WIAS_LTRACE
product:
- Windows
targetos: Windows
req.typenames: 
---

# WIAS_LTRACE macro

## -description

The WIAS_LTRACE macro is obsolete. It is recommended that the [WIAS_TRACE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_trace) macro be used instead.

The WIAS_LTRACE macro writes a diagnostic WIA_TRACE message to the log file.

## -parameters

### -param pILog

### -param ResID

### -param Detail

### -param Args

- **DetailLevel** - Specifies the diagnostic detail level of the message. This parameter can be one of the following values.

    | Value | Description |
    | --- | --- |
    | WIALOG_LEVEL1 | Logs entry and exit points for all WIA methods and functions. |
    | WIALOG_LEVEL2 | Logs additional details for WIALOG_LEVEL1. |
    | WIALOG_LEVEL3 | Logs entry and exit points for all WIA methods and functions and additional vendor-supplied functions. |
    | WIALOG_LEVEL4 | Logs additional details for WIALOG_LEVEL3. |
    | WIALOG_LEVELXXX | User-defined log levels. |

- **ResourceID** - Specifies the resource ID. This value should be set to WIALOG_NO_RESOURCE_ID.

- **format_string** - Specifies a variable argument list, which starts with an ANSI format string describing the message and any format identifiers. The ellipsis (...) specifies a variable number of arguments that need to be output. The error text should be prefixed with the full name of the method or function and generate the message in the format of "class::method, error-text".

- **pIWiaLog** - Pointer to an [IWiaLog Interface](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wia_lh/nn-wia_lh-iwialog).

## -remarks

The following is an example of how the macro can be used:

```cpp
WIAS_LTRACE(g_pIWiaLog, WIALOG_NO_RESOURCE_ID, WIALOG_LEVEL2,
  ("MyClass::MyMethod, This is my text and my lValue = %d", lValue));
```

The WIAS_LTRACE macro obsolete and is not recommended for use because it does not record its output to the *Wiatrace.log* diagnostic Log file. It is recommended that the [WIAS_TRACE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_trace) macro be used instead.

## -see-also

[WIAS_LERROR](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_lerror)

[WIAS_LHRESULT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_lhresult)

[WIAS_LWARNING](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_lwarning)

[WIAS_TRACE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_trace)
