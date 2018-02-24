---
UID: NE:storport._STOR_CRYPTO_ALGORITHM_ID
title: "_STOR_CRYPTO_ALGORITHM_ID"
author: windows-driver-content
description: Reserved for system use.
old-location: storage\stor_crypto_algorithm_id.htm
old-project: storage
ms.assetid: 761B905B-D8E5-43C2-A412-EEC5F91848F3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "_STOR_CRYPTO_ALGORITHM_ID, storage.stor_crypto_algorithm_id, storport/STOR_CRYPTO_ALGORITHM_ID, PSTOR_CRYPTO_ALGORITHM_ID enumeration pointer [Storage Devices], storport/, PSTOR_CRYPTO_ALGORITHM_ID, *PSTOR_CRYPTO_ALGORITHM_ID, storport/PSTOR_CRYPTO_ALGORITHM_ID, STOR_CRYPTO_ALGORITHM_ID enumeration [Storage Devices], STOR_CRYPTO_ALGORITHM_ID"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: storport.h
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
-	Storport.h
apiname:
-	STOR_CRYPTO_ALGORITHM_ID
product: Windows
targetos: Windows
req.typenames: "*PSTOR_CRYPTO_ALGORITHM_ID, STOR_CRYPTO_ALGORITHM_ID"
req.product: Windows 10 or later.
---

# _STOR_CRYPTO_ALGORITHM_ID enumeration


## -description


Reserved for system use


## -syntax


````
typedef enum _STOR_CRYPTO_ALGORITHM_ID { 
    = 
} STOR_CRYPTO_ALGORITHM_ID, *PSTOR_CRYPTO_ALGORITHM_ID;
````


## -enum-fields




### -field StorCryptoAlgorithmUnknown


### -field StorCryptoAlgorithmXTSAES


### -field StorCryptoAlgorithmBitlockerAESCBC


### -field StorCryptoAlgorithmAESECB


### -field StorCryptoAlgorithmESSIVAESCBC


### -field StorCryptoAlgorithmMax





