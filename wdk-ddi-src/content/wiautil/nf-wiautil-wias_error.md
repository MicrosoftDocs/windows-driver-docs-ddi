---
UID: NF:wiautil.WIAS_ERROR
title: WIAS_ERROR macro (wiautil.h)
description: The WIAS_ERROR macro writes a diagnostic message to the Wiatrace.log file.
old-location: image\wias_error.htm
tech.root: image
ms.assetid: e439f130-1b99-4f46-ace5-3456c09a5f67
ms.date: 05/03/2018
ms.keywords: IWiaLog_5b3e0d61-e0e5-4385-8256-943e437cee9d.xml, WIAS_ERROR, WIAS_ERROR macro [Imaging Devices], image.wias_error, wiamdef/WIAS_ERROR
ms.topic: macro
f1_keywords:
 - "wiautil/WIAS_ERROR"
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the operating system.
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
- WIAS_ERROR
product:
- Windows
targetos: Windows
req.typenames: 
---

# WIAS_ERROR macro

## -description

The WIAS_ERROR macro writes a diagnostic message to the *Wiatrace.log* file.

## -parameters

### -param x

- **HInst** - Handle to the DLL (driver).

- **format_string, ...** - Specifies a variable argument list, which starts with an ANSI format string that describes the message and any format identifiers. The ellipsis (...) specifies a variable number of arguments that need to be output. The error text should be prefixed with the full name of the method or function and generate the message in the format of "class::method, error-text".

## -remarks

This macro is the recommended way to implement error logging on Windows Vista, because unlike [WIAS_LERROR](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_lerror), WIA_ERROR allows error messages to be written to the log file (*Wiatrace.log*). The *Wiatrace.log* file is only available in Windows Vista and later versions of the operating system. The utility used to view the contents of this log file is WiaTrcVw.exe.

To enable tracing in free builds, drivers must define the WIA_DEBUG macro by adding `#define WIA_DEBUG` before including any of the WIA headers. Tracing is enabled by default in checked and debug builds of the operating system.

The following is an example of how the macro can be used:

```cpp
WIAS_ERROR((g_hInst, "Failed to read (%ws) entry under %ws section of device registry",REG_ENTRY_STORAGEPATH,REG_ENTRY_DEVICEDATA));
```

This code snippet was taken from [Wiadriver.cpp](https://github.com/Microsoft/Windows-driver-samples/blob/master/wia/wiadriverex/usd/wiadriver.cpp), which is included with the Windows Image Acquisition (WIA) driver samples on GitHub.

## -see-also

[WIAS_ASSERT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_assert)

[WIAS_HRESULT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_hresult)

[WIAS_TRACE](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamdef/nf-wiamdef-wias_trace)
