---
UID: NE:nfccx._NFC_CX_NFCIP_TGT_MODE_CONFIG
title: "_NFC_CX_NFCIP_TGT_MODE_CONFIG"
author: windows-driver-content
description: The NFC_CX_NFCIP_TGT_MODE_CONFIG enumeration specifies NFC-IP target mode.
old-location: nfpdrivers\nfc_cx_nfcip_tgt_mode_config.htm
old-project: nfpdrivers
ms.assetid: E689992B-C767-4942-871D-D6EEDA35F0E7
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PNFC_CX_NFCIP_TGT_MODE_CONFIG, NFC_CX_NFCIP_DEFAULT, NFC_CX_NFCIP_NFC_A, NFC_CX_NFCIP_NFC_ACTIVE, NFC_CX_NFCIP_NFC_ACTIVE_A, NFC_CX_NFCIP_NFC_ACTIVE_F_212, NFC_CX_NFCIP_NFC_ACTIVE_F_424, NFC_CX_NFCIP_NFC_F_212, NFC_CX_NFCIP_NFC_F_424, NFC_CX_NFCIP_TGT_MODE_CONFIG, NFC_CX_NFCIP_TGT_MODE_CONFIG enumeration [Near-Field Proximity Drivers], PNFC_CX_NFCIP_TGT_MODE_CONFIG, _NFC_CX_NFCIP_TGT_MODE_CONFIG, nfccx/NFC_CX_NFCIP_DEFAULT, nfccx/NFC_CX_NFCIP_NFC_A, nfccx/NFC_CX_NFCIP_NFC_ACTIVE, nfccx/NFC_CX_NFCIP_NFC_ACTIVE_A, nfccx/NFC_CX_NFCIP_NFC_ACTIVE_F_212, nfccx/NFC_CX_NFCIP_NFC_ACTIVE_F_424, nfccx/NFC_CX_NFCIP_NFC_F_212, nfccx/NFC_CX_NFCIP_NFC_F_424, nfccx/NFC_CX_NFCIP_TGT_MODE_CONFIG, nfpdrivers.nfc_cx_nfcip_tgt_mode_config"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
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
req.irql: Requires same
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	nfccx.h
api_name:
-	NFC_CX_NFCIP_TGT_MODE_CONFIG
product: Windows
targetos: Windows
req.typenames: NFC_CX_NFCIP_TGT_MODE_CONFIG, *PNFC_CX_NFCIP_TGT_MODE_CONFIG
---

# _NFC_CX_NFCIP_TGT_MODE_CONFIG enumeration


## -description


The NFC_CX_NFCIP_TGT_MODE_CONFIG enumeration specifies NFC-IP target mode.


## -syntax


````
typedef enum _NFC_CX_NFCIP_TGT_MODE_CONFIG { 
  NFC_CX_NFCIP_NFC_A             = 0x01,
  NFC_CX_NFCIP_NFC_F_212         = 0x02,
  NFC_CX_NFCIP_NFC_F_424         = 0x04,
  NFC_CX_NFCIP_NFC_ACTIVE        = 0x08,
  NFC_CX_NFCIP_NFC_ACTIVE_A      = 0x10,
  NFC_CX_NFCIP_NFC_ACTIVE_F_212  = 0x20,
  NFC_CX_NFCIP_NFC_ACTIVE_F_424  = 0x40,
  NFC_CX_NFCIP_DEFAULT           = NFC_CX_NFCIP_NFC_A | NFC_CX_NFCIP_NFC_F_212 | NFC_CX_NFCIP_NFC_F_424
} NFC_CX_NFCIP_TGT_MODE_CONFIG;
````


## -enum-fields




### -field NFC_CX_NFCIP_TGT_NFC_A


### -field NFC_CX_NFCIP_TGT_NFC_F


### -field NFC_CX_NFCIP_TGT_NFC_ACTIVE_A


### -field NFC_CX_NFCIP_TGT_NFC_ACTIVE_F


### -field NFC_CX_NFCIP_TGT_DEFAULT




#### - NFC_CX_NFCIP_DEFAULT


#### - NFC_CX_NFCIP_NFC_A


#### - NFC_CX_NFCIP_NFC_ACTIVE


#### - NFC_CX_NFCIP_NFC_ACTIVE_A


#### - NFC_CX_NFCIP_NFC_ACTIVE_F_212


#### - NFC_CX_NFCIP_NFC_ACTIVE_F_424


#### - NFC_CX_NFCIP_NFC_F_212


#### - NFC_CX_NFCIP_NFC_F_424


## -see-also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



 

 


