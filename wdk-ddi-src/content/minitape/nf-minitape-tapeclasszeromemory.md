---
UID: NF:minitape.TapeClassZeroMemory
title: TapeClassZeroMemory function (minitape.h)
description: The TapeClassZeroMemory routine fills a buffer with zeros.
old-location: storage\tapeclasszeromemory.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["TapeClassZeroMemory function"]
ms.keywords: TapeClassZeroMemory, TapeClassZeroMemory routine [Storage Devices], minitape/TapeClassZeroMemory, storage.tapeclasszeromemory, tapeclas_f48cbbef-af5f-4d1b-b79e-0982d4d09bde.xml
req.header: minitape.h
req.include-header: Minitape.h
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
req.lib: Tape.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - TapeClassZeroMemory
 - minitape/TapeClassZeroMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Tape.lib
 - Tape.dll
api_name:
 - TapeClassZeroMemory
---

# TapeClassZeroMemory function


## -description

The <b>TapeClassZeroMemory</b> routine fills a buffer with zeros.

## -parameters

### -param Buffer [in, out]


Pointer to the buffer that needs to be cleared.

### -param BufferSize [in]


Specifies the size of the buffer, in bytes.

## -returns

None

## -remarks

A tape miniclass driver calls <b>TapeClassZeroMemory</b> to zero a buffer in a portable way. A miniclass driver must use <b>TapeClassZeroMemory</b> to clear the TAPE_INIT_DATA_EX structure and CDBs before it uses them.

## -see-also

<a href="/windows-hardware/drivers/storage/driverentry-of-tape-miniclass-driver">DriverEntry of Tape Miniclass Driver</a>
