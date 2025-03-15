---
UID: NF:rxlog._RxLog
title: _RxLog function (rxlog.h)
description: Learn more about the _RxLog function.
tech.root: ifsk
ms.date: 10/30/2024
keywords: ["RxLog function"]
req.header: rxlog.h
req.include-header: Rxlog.h
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - _RxLog
 - rxlog/_RxLog
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rxlog.h
api_name:
 - _RxLog
---

# _RxLog function

## -description

**_RxLog** is a part of the RDBSS (Redirected Drive Buffering SubSystem) debug logging facilities. It takes a format string and variable number of parameters and formats an output string for recording as an I/O error log entry if logging is enabled.

## -parameters

### -param format

Pointer to a variable argument list that contains a format string and a variable number of format specifiers that are replaced by the values of subsequent arguments.

### -param ...

Variable number of arguments that correspond to the format specifies in the **format** string. These arguments provide the data to be logged, such as strings, integers, and so forth.

## -remarks

It is recommended that the **RxLog** macro be used instead of calling the **_RxLog** routine directly. On retail builds, the **RxLog** macro is defined to nothing.

If logging is enabled, **_RxLog** will output a string for recording as an I/O error log entry based on the format string and number of variables passed.

The **_RxLog** routine supports the following format string descriptors:

* %lN, %wN, %lS, %wS, %ld, %wd--a number
* %x--a hexadecimal number
* %c--a character
* %s--an ASCII string
* %Z--a Unicode string that contains ASCII characters

The **_RxLog** routine is limited to an output string of, at most, 48 lines, so the **format** string can't contain more than 48 '\n' characters.

## -see-also

[**RxLogEventDirect**](../rxprocs/nf-rxprocs-rxlogeventdirect.md)

[**RxLogEventWithAnnotation**](../rxprocs/nf-rxprocs-rxlogeventwithannotation.md)

[**RxLogEventWithBufferDirect**](../rxprocs/nf-rxprocs-rxlogeventwithbufferdirect.md)
