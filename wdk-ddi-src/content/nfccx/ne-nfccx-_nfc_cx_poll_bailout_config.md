---
UID: NE:nfccx._NFC_CX_POLL_BAILOUT_CONFIG
title: "_NFC_CX_POLL_BAILOUT_CONFIG"
author: windows-driver-content
description: The NFC_CX_POLL_BAILOUT_CONFIG enumeration specifies poll mode bail out.
old-location: nfpdrivers\nfc_cx_poll_bailout_config.htm
old-project: nfpdrivers
ms.assetid: 1085EA0A-B688-4F77-80AF-E81CFE645CDF
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: NFC_CX_POLL_BAILOUT_NFC_A, *PNFC_CX_POLL_BAILOUT_CONFIG, nfccx/NFC_CX_POLL_BAILOUT_NFC_A, NFC_CX_POLL_BAILOUT_CONFIG, *PNFC_CX_POLL_BAILOUT_CONFIG, nfccx/NFC_CX_POLL_BAILOUT_NFC_B, nfccx/NFC_CX_POLL_BAILOUT_CONFIG, NFC_CX_POLL_BAILOUT_NFC_B, nfccx/NFC_CX_POLL_BAILOUT_DEFAULT, NFC_CX_POLL_BAILOUT_CONFIG, _NFC_CX_POLL_BAILOUT_CONFIG, nfpdrivers.nfc_cx_poll_bailout_config, NFC_CX_POLL_BAILOUT_CONFIG enumeration [Near-Field Proximity Drivers], NFC_CX_POLL_BAILOUT_DEFAULT, NFC_CX_POLL_BAILOUT_CONFIG, *PNFC_CX_POLL_BAILOUT_CONFIG enumeration [Near-Field Proximity Drivers]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	nfccx.h
apiname:
-	NFC_CX_POLL_BAILOUT_CONFIG, *PNFC_CX_POLL_BAILOUT_CONFIG
product: Windows
targetos: Windows
req.typenames: NFC_CX_POLL_BAILOUT_CONFIG, *PNFC_CX_POLL_BAILOUT_CONFIG
---

# _NFC_CX_POLL_BAILOUT_CONFIG enumeration


## -description


The NFC_CX_POLL_BAILOUT_CONFIG enumeration specifies poll mode bail out.


## -syntax


````
typedef enum _NFC_CX_POLL_BAILOUT_CONFIG { 
  NFC_CX_POLL_BAILOUT_NFC_A    = 0x01,
  NFC_CX_POLL_BAILOUT_NFC_B    = 0x02,
  NFC_CX_POLL_BAILOUT_DEFAULT  = 0x00
} NFC_CX_POLL_BAILOUT_CONFIG, *PNFC_CX_POLL_BAILOUT_CONFIG;
````


## -enum-fields




### -field NFC_CX_POLL_BAILOUT_DEFAULT



### -field NFC_CX_POLL_BAILOUT_NFC_A



### -field NFC_CX_POLL_BAILOUT_NFC_B



## -see-also

<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NFC_CX_POLL_BAILOUT_CONFIG enumeration%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

