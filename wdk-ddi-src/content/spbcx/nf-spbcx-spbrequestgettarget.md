---
UID: NF:spbcx.SpbRequestGetTarget
title: SpbRequestGetTarget function (spbcx.h)
description: The SpbRequestGetTarget method retrieves the SPBTARGET handle from the specified I/O request.
old-location: spb\spbrequestgettarget.htm
tech.root: SPB
ms.date: 04/30/2018
keywords: ["SpbRequestGetTarget function"]
ms.keywords: SPB.spbrequestgettarget, SpbRequestGetTarget, SpbRequestGetTarget method [Buses], spbcx/SpbRequestGetTarget
req.header: spbcx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Spbcxstubs.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SpbRequestGetTarget
 - spbcx/SpbRequestGetTarget
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - spbcxstubs.lib
 - spbcxstubs.dll
api_name:
 - SpbRequestGetTarget
---

# SpbRequestGetTarget function


## -description

The <b>SpbRequestGetTarget</b> method retrieves the SPBTARGET handle from the specified I/O request.

## -parameters

### -param SpbRequest 

[in]
An <a href="/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a> handle to the I/O request. The SPB controller driver previously received this handle through one of its registered <a href="/previous-versions/hh450911(v=vs.85)">event callback functions</a>.

## -returns

<b>SpbRequestGetTarget</b> returns an <a href="/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a> handle to the target device on the bus for the specified I/O request.

## -remarks

The returned SPBTARGET handle is guaranteed to remain valid until the corresponding I/O request is completed.

## -see-also

<a href="/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a>



<a href="/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a>
