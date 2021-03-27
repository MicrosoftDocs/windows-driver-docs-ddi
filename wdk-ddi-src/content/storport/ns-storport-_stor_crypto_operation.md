---
UID: NS:storport._STOR_CRYPTO_OPERATION
title: _STOR_CRYPTO_OPERATION (storport.h)
description: STOR_CRYPTO_OPERATION is the structure pointed to by the Parameters parameter when a miniport's HwStorAdapterControl routine is called with a ControlType of ScsiAdapterCryptoOperation.
tech.root: storage
ms.date: 05/13/2021
keywords: ["STOR_CRYPTO_OPERATION structure"]
ms.keywords: _STOR_CRYPTO_OPERATION, STOR_CRYPTO_OPERATION, *PSTOR_CRYPTO_OPERATION,
req.header: storport.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: STOR_CRYPTO_OPERATION, *PSTOR_CRYPTO_OPERATION
targetos: Windows
f1_keywords:
 - _STOR_CRYPTO_OPERATION
 - storport/_STOR_CRYPTO_OPERATION
 - PSTOR_CRYPTO_OPERATION
 - storport/PSTOR_CRYPTO_OPERATION
 - STOR_CRYPTO_OPERATION
 - storport/STOR_CRYPTO_OPERATION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_CRYPTO_OPERATION
 - PSTOR_CRYPTO_OPERATION
 - STOR_CRYPTO_OPERATION
---

## -description

**STOR_CRYPTO_OPERATION** is the structure pointed to by the **Parameters** parameter when a miniport's [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) routine is called with a **ControlType** of **ScsiAdapterCryptoOperation**.

## -struct-fields

### -field OperationType

A [**STOR_CRYPTO_OPERATION_TYPE**](ne-storport-_stor_crypto_operation_type.md) value.

### -field OperationBufferLength

Length of the buffer that **OperationBuffer** points to, in bytes.

### -field OperationBuffer

Pointer to a buffer containing the payload for the operation.

## -remarks

## -see-also

[**HwStorAdapterControl**](nc-storport-hw_adapter_control.md)
