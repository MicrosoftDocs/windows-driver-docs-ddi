---
UID: NF:wiautil.WIAS_TRACE
title: WIAS_TRACE macro (wiautil.h)
description: The WIAS_TRACE macro writes a diagnostic message to the Wiatrace.log file.
old-location: image\wias_trace.htm
tech.root: image
ms.assetid: 9f6b06bf-60d3-4ec2-8c49-405bff2ccb5e
ms.date: 05/03/2018
keywords: ["WIAS_TRACE macro"]
ms.keywords: IWiaLog_c755ea6c-c312-4b15-be83-a437358b83a9.xml, WIAS_TRACE, WIAS_TRACE macro [Imaging Devices], image.wias_trace, wiamdef/WIAS_TRACE
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
 - WIAS_TRACE
 - wiautil/WIAS_TRACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wiamdef.h
api_name:
 - WIAS_TRACE
---

# WIAS_TRACE macro (wiautil.h)


## -description

The WIAS_TRACE macro writes a diagnostic message to the*Wiatrace.log* file.

## -parameters

### -param x

- **HInst** - Handle to the DLL (driver).

- **format_string, ...** - Specifies a variable argument list, which starts with an ANSI format string that describes the message and any format identifiers. The ellipsis (...) specifies a variable number of arguments that need to be output. The error text should be prefixed with the full name of the method or function and generate the message in the format of "class::method, error-text".

## -remarks

To enable tracing in free builds, drivers must define the WIA_DEBUG macro by adding `#define WIA_DEBUG` before including any of the WIA headers. Tracing is enabled by default in checked and debug builds of the operating system.

The following is an example of how the macro would be used:

```cpp
WIAS_TRACE((g_hInst,"WIA storage path = %ws",m_wszStoragePath));
```

This code snippet was taken from*Wiadriver.cpp*, which is included with the WDK.

## -see-also

[WIAS_ASSERT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wias_assert)

[WIAS_ERROR](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wias_error)

[WIAS_HRESULT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wias_hresult)

