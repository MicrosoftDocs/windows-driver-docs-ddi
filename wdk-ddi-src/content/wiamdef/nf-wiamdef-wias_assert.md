---
UID: NF:wiamdef.WIAS_ASSERT
title: WIAS_ASSERT macro (wiamdef.h)
description: The WIAS_ASSERT macro writes a diagnostic message to the Wiatrace.log file.
old-location: image\wias_assert.htm
tech.root: image
ms.assetid: 74dac8e1-a909-4c22-a650-af8a43421c5c
ms.date: 05/03/2018
ms.keywords: IWiaLog_91198444-77d8-4f41-957b-de4c3262988a.xml, WIAS_ASSERT, WIAS_ASSERT macro [Imaging Devices], image.wias_assert, wiamdef/WIAS_ASSERT
f1_keywords:
 - "wiamdef/WIAS_ASSERT"
req.header: wiamdef.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wiamdef.h
api_name:
- WIAS_ASSERT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WIAS_ASSERT macro

## -description

The WIAS_ASSERT macro writes a diagnostic message to the *Wiatrace.log* file.

## -parameters

### -param x

### -param y

#### - Expression

Specifies any logical expression.

#### - HInst

Handle to the DLL (driver).

## -remarks

The WIAS_ASSERT macro is used to debug WIA drivers. It is used to test that a certain condition is met. If the *Expression* parameter evaluates to **TRUE**, this macro does nothing. If *Expression* evaluates to **FALSE**, the macro prints an error string to the *Wiatrace.log* diagnostic log file. This error message will contain the name and path to the calling driver and the line number in the driver source code where the WIAS_ASSERT macro failed.

The WIAS_ASSERT macro is available in Windows Vista and later versions of the operating system. This macro is the recommended way to implement WIA assertions on Windows Vista. WIAS_ASSERT allows error messages to be written to the log file (*Wiatrace.log*). The *Wiatrace.log* file is only available in Windows Vista, and later versions of the operating system. The utility used to view the contents of this log file is WiaTrcVw.exe.

To enable asserts in free builds, drivers must define the WIA_DEBUG macro by adding `#define WIA_DEBUG` to the driver's source code; this must be done before including any of the WIA headers. Asserts are enabled by default in checked and debug builds of the operating system.

## -see-also

[WIAS_ERROR](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wias_error)

[WIAS_HRESULT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wias_hresult)

[WIAS_TRACE](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wias_trace)
