---
UID: NF:sensorsdriversutils.I2CSensorReadRegister
title: I2CSensorReadRegister function (sensorsdriversutils.h)
description: The I2CSensorReadRegister function reads the devices register(s) over I2C.
ms.assetid: fda9f6f9-7cd5-4df2-9654-6d604e0e617e
ms.date: 04/19/2018
keywords: ["I2CSensorReadRegister function"]
ms.keywords: I2CSensorReadRegister
req.header: sensorsdriversutils.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - I2CSensorReadRegister
 - sensorsdriversutils/I2CSensorReadRegister
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - I2CSensorReadRegister
product:
 - Windows
---

# I2CSensorReadRegister function


## -description

The I2CSensorReadRegister function reads the devices register(s) over I2C.

## -parameters

### -param I2CIoTarget

Supplies the WDF I2C I/O target handle.

### -param RegAddress

Supplies the I2C register address to read from.

### -param Buffer

Supplies a buffer in which to read the contents of the register to.

### -param BufferCb

Supplies the size of the buffer.

## -returns

This function returns NTSTATUS.

## -remarks

## -see-also

