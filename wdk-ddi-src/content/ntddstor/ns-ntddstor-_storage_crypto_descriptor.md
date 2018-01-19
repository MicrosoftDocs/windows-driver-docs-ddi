---
UID: NS:ntddstor._STORAGE_CRYPTO_DESCRIPTOR
title: _STORAGE_CRYPTO_DESCRIPTOR
author: windows-driver-content
description: Reserved for system use.
old-location: storage\storage_crypto_descriptor.htm
old-project: storage
ms.assetid: 1D948882-2286-4080-A41B-D20714FC0A66
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _STORAGE_CRYPTO_DESCRIPTOR, *PSTORAGE_CRYPTO_DESCRIPTOR, STORAGE_CRYPTO_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_CRYPTO_DESCRIPTOR
req.alt-loc: Ntddstor.h
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
req.typenames: *PSTORAGE_CRYPTO_DESCRIPTOR, STORAGE_CRYPTO_DESCRIPTOR
---

# _STORAGE_CRYPTO_DESCRIPTOR structure



## -description
Reserved for system use.



## -syntax

````
typedef struct _STORAGE_CRYPTO_DESCRIPTOR {
  DWORD                                                          Version;
  DWORD                                                          Size;
  DWORD                                                          NumKeysSupported;
  DWORD                                                          NumCryptoCapabilities;
   _Field_size_(NumCryptoCapabilities) STORAGE_CRYPTO_CAPABILITY CryptoCapabilities[ANYSIZE_ARRAY];
} STORAGE_CRYPTO_DESCRIPTOR, *PSTORAGE_CRYPTO_DESCRIPTOR;
````


## -struct-fields

### -field Version

Reserved for system use.


### -field Size

Reserved for system use.


### -field NumKeysSupported

Reserved for system use.


### -field NumCryptoCapabilities

Reserved for system use.


### -field CryptoCapabilities

Reserved for system use.


## -remarks
