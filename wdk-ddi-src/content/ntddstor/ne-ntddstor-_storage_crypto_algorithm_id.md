---
UID: NE:ntddstor._STORAGE_CRYPTO_ALGORITHM_ID
title: "_STORAGE_CRYPTO_ALGORITHM_ID"
author: windows-driver-content
description: The STORAGE_CRYPTO_ALGORITHM_ID enum provides an output buffer for StorageAdapterCryptoProperty and PropertyStandardQuery.
old-location: storage\storage_crypto_algorithm_id.htm
old-project: storage
ms.assetid: 5D1CCF3D-D677-47B0-9C7B-7E35C649A7D5
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddstor/StorageCryptoAlgorithmAESECB, STORAGE_CRYPTO_ALGORITHM_ID, *PSTORAGE_CRYPTO_ALGORITHM_ID, StorageCryptoAlgorithmXTSAES, StorageCryptoAlgorithmAESECB, *PSTORAGE_CRYPTO_ALGORITHM_ID, ntddstor/StorageCryptoAlgorithmXTSAES, StorageCryptoAlgorithmESSIVAESCBC, StorageCryptoAlgorithmUnknown, ntddstor/StorageCryptoAlgorithmMax, ntddstor/StorageCryptoAlgorithmUnknown, StorageCryptoAlgorithmMax, storage.storage_crypto_algorithm_id, ntddstor/StorageCryptoAlgorithmESSIVAESCBC, STORAGE_CRYPTO_ALGORITHM_ID, *PSTORAGE_CRYPTO_ALGORITHM_ID enumeration [Storage Devices], _STORAGE_CRYPTO_ALGORITHM_ID, STORAGE_CRYPTO_ALGORITHM_ID, StorageCryptoAlgorithmBitlockerAESCBC, ntddstor/STORAGE_CRYPTO_ALGORITHM_ID, STORAGE_CRYPTO_ALGORITHM_ID enumeration [Storage Devices], ntddstor/StorageCryptoAlgorithmBitlockerAESCBC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddstor.h
apiname:
-	STORAGE_CRYPTO_ALGORITHM_ID, *PSTORAGE_CRYPTO_ALGORITHM_ID
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_CRYPTO_ALGORITHM_ID, STORAGE_CRYPTO_ALGORITHM_ID"
---

# _STORAGE_CRYPTO_ALGORITHM_ID enumeration


## -description


The <b>STORAGE_CRYPTO_ALGORITHM_ID</b> enum provides an output buffer for <b>StorageAdapterCryptoProperty</b> and <b>PropertyStandardQuery</b>.


## -syntax


````
typedef enum _STORAGE_CRYPTO_ALGORITHM_ID { 
  StorageCryptoAlgorithmUnknown          = 0,
  StorageCryptoAlgorithmXTSAES           = 1,
  StorageCryptoAlgorithmBitlockerAESCBC,
  StorageCryptoAlgorithmAESECB,
  StorageCryptoAlgorithmESSIVAESCBC,
  StorageCryptoAlgorithmMax
} STORAGE_CRYPTO_ALGORITHM_ID, *PSTORAGE_CRYPTO_ALGORITHM_ID;
````


## -enum-fields




### -field StorageCryptoAlgorithmUnknown

Reserved for system use.


### -field StorageCryptoAlgorithmXTSAES

Reserved for system use.


### -field StorageCryptoAlgorithmBitlockerAESCBC

Reserved for system use.


### -field StorageCryptoAlgorithmAESECB

Reserved for system use.


### -field StorageCryptoAlgorithmESSIVAESCBC

Reserved for system use.


### -field StorageCryptoAlgorithmMax

Reserved for system use.

