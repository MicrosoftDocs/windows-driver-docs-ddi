---
UID: NE:nfccx._NFC_CX_HOST_ACTION
title: _NFC_CX_HOST_ACTION
author: windows-driver-content
description: The NFC_CX_HOST_ACTION enumeration specifies host actions.
old-location: nfpdrivers\nfc_cx_host_action.htm
old-project: nfpdrivers
ms.assetid: CE485A6F-8480-4535-9145-A8CBF78C804D
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: HostActionUnload, NFC_CX_HOST_ACTION, nfccx/HostActionStop, nfpdrivers.nfc_cx_host_action, nfccx/NFC_CX_HOST_ACTION, HostActionRestart, nfccx/HostActionStart, nfccx/HostActionUnload, *PNFC_CX_HOST_ACTION, NFC_CX_HOST_ACTION enumeration [Near-Field Proximity Drivers], HostActionStart, HostActionStop, nfccx/HostActionRestart, _NFC_CX_HOST_ACTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: nfccx.h
req.include-header: 
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
-	NFC_CX_HOST_ACTION
product: Windows
targetos: Windows
req.typenames: *PNFC_CX_HOST_ACTION, NFC_CX_HOST_ACTION
---

# _NFC_CX_HOST_ACTION enumeration


## -description


The NFC_CX_HOST_ACTION enumeration specifies host actions.


## -syntax


````
typedef enum _NFC_CX_HOST_ACTION { 
  HostActionStart    = 0,
  HostActionStop     = 1,
  HostActionRestart  = 2,
  HostActionUnload   = 3
} NFC_CX_HOST_ACTION;
````


## -enum-fields




### -field HostActionStart

Specifies full initialization.


### -field HostActionStop

Specifies de-initialization.


### -field HostActionRestart

Specifies a full driver restart.


### -field HostActionUnload

Specifies to unload the driver.


## -see-also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>

<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20NFC_CX_HOST_ACTION enumeration%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

