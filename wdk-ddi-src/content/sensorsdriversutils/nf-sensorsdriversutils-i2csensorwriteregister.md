---
UID: NF:sensorsdriversutils.I2CSensorWriteRegister
title: I2CSensorWriteRegister function (sensorsdriversutils.h)
description: The I2CSensorWriteRegister function writes to the device register(s) over I2C.
ms.assetid: 066fda1c-63c2-451b-bead-6787eeaf49b0
ms.date: 04/19/2018
keywords: ["I2CSensorWriteRegister function"]
ms.keywords: I2CSensorWriteRegister
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
 - I2CSensorWriteRegister
 - sensorsdriversutils/I2CSensorWriteRegister
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - I2CSensorWriteRegister
product:
 - Windows
---

# I2CSensorWriteRegister function


## -description

The I2CSensorWriteRegister function writes to the device register(s) over I2C.

## -parameters

### -param I2CIoTarget

Supplies the WDF I2C I/O target handle.

### -param RegAddress

Supplies the I2C register address to write to.

### -param RegValue

Supplies the value to write.

### -param RegLength

Number of bytes contained in RegValue array.

## -returns

This function returns NTSTATUS.

## -remarks

## -see-also

