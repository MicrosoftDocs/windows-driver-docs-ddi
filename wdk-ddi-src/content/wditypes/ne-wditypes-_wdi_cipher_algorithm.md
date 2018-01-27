---
UID: NE:wditypes._WDI_CIPHER_ALGORITHM
title: _WDI_CIPHER_ALGORITHM
author: windows-driver-content
description: The WDI_CIPHER_ALGORITHM enumeration defines the cipher algorithm values.
old-location: netvista\wdi_cipher_algorithm.htm
old-project: netvista
ms.assetid: 08413358-DFBC-4AC3-97B3-380D98EFFBF3
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WDI_CIPHER_ALGO_WEP40, wditypes/WDI_CIPHER_ALGO_CCMP, WDI_CIPHER_ALGO_WEP104, WDI_CIPHER_ALGO_WPA_USE_GROUP, WDI_CIPHER_ALGO_TKIP, wditypes/WDI_CIPHER_ALGO_WEP104, WDI_CIPHER_ALGO_IHV_START, WDI_CIPHER_ALGO_GCMP, wditypes/WDI_CIPHER_ALGO_WPA_USE_GROUP, wditypes/WDI_CIPHER_ALGO_IHV_START, netvista.wifi_cipher_algorithm, WDI_CIPHER_ALGO_RSN_USE_GROUP, WDI_CIPHER_ALGO_BIP, WDI_CIPHER_ALGO_NONE, WDI_CIPHER_ALGO_CCMP, wditypes/WDI_CIPHER_ALGO_IHV_END, wditypes/WDI_CIPHER_ALGO_BIP, netvista.wdi_cipher_algorithm, wditypes/WDI_CIPHER_ALGO_WEP, wditypes/WDI_CIPHER_ALGORITHM, wditypes/WDI_CIPHER_ALGO_TKIP, WDI_CIPHER_ALGORITHM, WDI_CIPHER_ALGO_WEP, WDI_CIPHER_ALGORITHM enumeration [Device and Driver Installation], wditypes/WDI_CIPHER_ALGO_RSN_USE_GROUP, wditypes/WDI_CIPHER_ALGO_WEP40, wditypes/WDI_CIPHER_ALGO_GCMP, _WDI_CIPHER_ALGORITHM, WDI_CIPHER_ALGO_IHV_END, wditypes/WDI_CIPHER_ALGO_NONE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	wditypes.hpp
apiname: 
-	WDI_CIPHER_ALGORITHM
product: Windows
targetos: Windows
req.typenames: WDI_CIPHER_ALGORITHM
req.product: Windows 10 or later.
---

# _WDI_CIPHER_ALGORITHM enumeration


## -description


The WDI_CIPHER_ALGORITHM enumeration defines the cipher algorithm values.


## -syntax


````
typedef enum _WDI_CIPHER_ALGORITHM { 
  WDI_CIPHER_ALGO_NONE           = 0x00,
  WDI_CIPHER_ALGO_WEP40          = 0x01,
  WDI_CIPHER_ALGO_TKIP           = 0x02,
  WDI_CIPHER_ALGO_CCMP           = 0x04,
  WDI_CIPHER_ALGO_WEP104         = 0x05,
  WDI_CIPHER_ALGO_BIP            = 0x06,
  WDI_CIPHER_ALGO_GCMP           = 0x08,
  WDI_CIPHER_ALGO_WPA_USE_GROUP  = 0x100,
  WDI_CIPHER_ALGO_RSN_USE_GROUP  = 0x100,
  WDI_CIPHER_ALGO_WEP            = 0x101,
  WDI_CIPHER_ALGO_IHV_START      = 0x80000000,
  WDI_CIPHER_ALGO_IHV_END        = 0xffffffff
} WDI_CIPHER_ALGORITHM;
````


## -enum-fields




### -field WDI_CIPHER_ALGO_NONE

Specifies that no cipher algorithm is enabled or supported.


### -field WDI_CIPHER_ALGO_WEP40

Specifies a Wired Equivalent Privacy (WEP) algorithm, which is the RC4-based algorithm that is specified in the IEEE 802.11-2012 standard. This enumerator specifies the WEP cipher algorithm with a 40-bit cipher key.


### -field WDI_CIPHER_ALGO_TKIP

Specifies a Temporal Key Integrity Protocol (TKIP) algorithm, which is the RC4-based cipher suite that is based on the algorithms that are defined in the WPA specification and IEEE 802.11i-2004 standard. This cipher also uses the Michael Message Integrity Code (MIC) algorithm for forgery protection.


### -field WDI_CIPHER_ALGO_CCMP

Specifies an AES-CCMP algorithm, as specified in the IEEE 802.11i-2004 standard and RFC 3610. Advanced Encryption Standard (AES) is the encryption algorithm defined in FIPS PUB 197.


### -field WDI_CIPHER_ALGO_WEP104

Specifies a WEP cipher algorithm with a 104-bit cipher key.


### -field WDI_CIPHER_ALGO_BIP

Specifies a BIP cipher algorithm.


### -field WDI_CIPHER_ALGO_GCMP

Added in Windows 10, version 1607, WDI version 1.0.21.

Specifies a GCMP (Galois/Counter Mode Protocol) cipher algorithm. It is the only encryption protocol supported for 802.11ad (DMG) Phy.


### -field WDI_CIPHER_ALGO_WPA_USE_GROUP

Specifies a Wi-Fi Protected Access (WPA) Use Group Key cipher suite. For more information about the Use Group Key cipher suite, refer to Clause 7.3.2.25.1 of the IEEE 802.11i-2004 standard.




### -field WDI_CIPHER_ALGO_RSN_USE_GROUP

Specifies a Robust Security Network (RSN) Use Group Key cipher suite. For more information about the Use Group Key cipher suite, refer to Clause 7.3.2.25.1 of the IEEE 802.11i-2004 standard.




### -field WDI_CIPHER_ALGO_WEP

Specifies a WEP cipher algorithm with a cipher key of any length. 


### -field WDI_CIPHER_ALGO_IHV_START

Specifies the start of the range that is used to define proprietary cipher algorithms that are developed by an independent hardware vendor (IHV). 




### -field WDI_CIPHER_ALGO_IHV_END

Specifies the end of the range that is used to define proprietary authentication algorithms that are developed by an IHV.  

