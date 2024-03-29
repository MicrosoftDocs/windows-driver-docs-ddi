---
UID: NF:ks.KsCreateClock2
title: KsCreateClock2 function (ks.h)
description: Creates a handle to a clock instance. Call this function after the Component Object Model (COM) is initialized.
old-location: stream\kscreateclock2.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsCreateClock2 function"]
ms.keywords: KsCreateClock2, KsCreateClock2 function [Streaming Media Devices], ks/KsCreateClock2, stream.kscreateclock2
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsCreateClock2
 - ks/KsCreateClock2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ks.h
api_name:
 - KsCreateClock2
---

# KsCreateClock2 function


## -description

Creates a handle to a clock instance. Call this function after the Component Object Model (COM) is initialized.

Supported starting in Windows 8.

## -parameters

### -param ConnectionHandle [in]


Specifies the handle to the connection on which to create the clock.

### -param ClockCreate [in]


Specifies clock create parameters. This currently consists of a flag that must be set to zero.

### -param ClockHandle [out]


Specifies the new clock handle.

## -returns

Returns <b>NOERROR</b> if successful; otherwise, returns an error code.

## -remarks

This is a new version of the <a href="/windows-hardware/drivers/ddi/ks/nf-ks-kscreateclock">KsCreateClock</a> function and uses the device broker to create the handle to the kernel streaming object. In addition, the COM <a href="/windows/win32/api/objbase/nf-objbase-coinitialize">CoInitialize</a> function must be called before this function is called.

## -see-also

<a href="/windows/win32/api/objbase/nf-objbase-coinitialize">CoInitialize</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kscreateclock">KsCreateClock</a>
