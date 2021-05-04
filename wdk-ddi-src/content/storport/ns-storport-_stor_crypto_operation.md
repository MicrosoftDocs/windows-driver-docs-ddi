---
UID: NS:storport._STOR_CRYPTO_OPERATION
title: STOR_CRYPTO_OPERATION (storport.h)
description: Reserved for system use.
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

Reserved for system use.

## -struct-fields

### -field OperationType

Reserved for system use.

### -field OperationBufferLength

Reserved for system use.

### -field OperationBuffer

Reserved for system use.

## -remarks

Structure pointed to by the **Parameters** parameter when a miniport's [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) routine is called with a **ControlType** of **ScsiAdapterCryptoOperation**.
