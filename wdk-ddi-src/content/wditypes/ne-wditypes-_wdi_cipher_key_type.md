---
UID: NE:wditypes._WDI_CIPHER_KEY_TYPE
title: "_WDI_CIPHER_KEY_TYPE"
author: windows-driver-content
description: The WDI_CIPHER_KEY_TYPE enumeration defines the cipher key types.
old-location: netvista\wdi_cipher_key_type.htm
old-project: netvista
ms.assetid: 09874F77-5A9C-4C98-996F-29BB90CAE4B6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WDI_CIPHER_KEY_TYPE, WDI_CIPHER_KEY_TYPE_PAIRWISE_KEY, netvista.wdi_cipher_key_type, _WDI_CIPHER_KEY_TYPE, wditypes/WDI_CIPHER_KEY_TYPE_PAIRWISE_KEY, wditypes/WDI_CIPHER_KEY_TYPE_IGTK, wditypes/WDI_CIPHER_KEY_TYPE_GROUP_KEY, WDI_CIPHER_KEY_TYPE_GROUP_KEY, WDI_CIPHER_KEY_TYPE_IGTK, wditypes/WDI_CIPHER_KEY_TYPE, WDI_CIPHER_KEY_TYPE enumeration [Device and Driver Installation], netvista.wifi_cipher_key_type
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
-	WDI_CIPHER_KEY_TYPE
product: Windows
targetos: Windows
req.typenames: WDI_CIPHER_KEY_TYPE
req.product: Windows 10 or later.
---

# _WDI_CIPHER_KEY_TYPE enumeration


## -description


The WDI_CIPHER_KEY_TYPE enumeration defines the cipher key types.


## -syntax


````
typedef enum _WDI_CIPHER_KEY_TYPE { 
  WDI_CIPHER_KEY_TYPE_PAIRWISE_KEY  = 1,
  WDI_CIPHER_KEY_TYPE_GROUP_KEY     = 2,
  WDI_CIPHER_KEY_TYPE_IGTK          = 3
} WDI_CIPHER_KEY_TYPE;
````


## -enum-fields




#### - WDI_CIPHER_KEY_TYPE_PAIRWISE_KEY

The key is a pairwise key to another station.


#### - WDI_CIPHER_KEY_TYPE_GROUP_KEY

The key is a group key.


#### - WDI_CIPHER_KEY_TYPE_IGTK

The key is an IGTK.

