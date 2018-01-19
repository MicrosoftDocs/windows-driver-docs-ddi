---
UID: NE:ntddrilapitypes.RILUNSOLICITEDSSINFONOTIFICATIONCODE
title: RILUNSOLICITEDSSINFONOTIFICATIONCODE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilunsolicitedssinfonotificationcode.htm
old-project: netvista
ms.assetid: 03dd4659-29fc-4426-8d30-2bbc0b71f899
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILUNSOLICITEDSSINFONOTIFICATIONCODE, RILUNSOLICITEDSSINFONOTIFICATIONCODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILUNSOLICITEDSSINFONOTIFICATIONCODE
req.alt-loc: ntddrilapitypes.h
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
req.typenames: RILUNSOLICITEDSSINFONOTIFICATIONCODE
---

# RILUNSOLICITEDSSINFONOTIFICATIONCODE enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RILUNSOLICITEDSSINFONOTIFICATIONCODE { 
  RIL_UNSSSCODE_CUGCALL,
  RIL_UNSSSCODE_CALLPUTONHOLD,
  RIL_UNSSSCODE_CALLRETRIEVED,
  RIL_UNSSSCODE_ENTEREDMULTIPARTY,
  RIL_UNSSSCODE_HELDCALLRELEASED,
  RIL_UNSSSCODE_FORWARDCHECKSS,
  RIL_UNSSSCODE_ALERTINGEXPLICITCALLXFER,
  RIL_UNSSSCODE_CONNECTEDEXPLICITCALLXFER,
  RIL_UNSSSCODE_DEFLECTEDCALL,
  RIL_UNSSSCODE_ADDITIONALINCOMINGCF,
  RIL_UNSSSCODE_UNCONDITIONALCFACTIVE,
  RIL_UNSSSCODE_SOMECONDITIONALCFACTIVE,
  RIL_UNSSSCODE_CALLWASFORWARDED,
  RIL_UNSSSCODE_CALLISWAITING,
  RIL_UNSSSCODE_OUTGOINGCALLSBARRED,
  RIL_UNSSSCODE_INCOMINGCALLSBARRED,
  RIL_UNSSSCODE_CLIRSUPPRESSREJECT,
  RIL_UNSSSCODE_MAX
} RILUNSOLICITEDSSINFONOTIFICATIONCODE;
````


## -enum-fields

### -field RIL_UNSSSCODE_CUGCALL


### -field RIL_UNSSSCODE_CALLPUTONHOLD


### -field RIL_UNSSSCODE_CALLRETRIEVED


### -field RIL_UNSSSCODE_ENTEREDMULTIPARTY


### -field RIL_UNSSSCODE_HELDCALLRELEASED


### -field RIL_UNSSSCODE_FORWARDCHECKSS


### -field RIL_UNSSSCODE_ALERTINGEXPLICITCALLXFER


### -field RIL_UNSSSCODE_CONNECTEDEXPLICITCALLXFER


### -field RIL_UNSSSCODE_DEFLECTEDCALL


### -field RIL_UNSSSCODE_ADDITIONALINCOMINGCF


### -field RIL_UNSSSCODE_UNCONDITIONALCFACTIVE


### -field RIL_UNSSSCODE_SOMECONDITIONALCFACTIVE


### -field RIL_UNSSSCODE_CALLWASFORWARDED


### -field RIL_UNSSSCODE_CALLISWAITING


### -field RIL_UNSSSCODE_OUTGOINGCALLSBARRED


### -field RIL_UNSSSCODE_INCOMINGCALLSBARRED


### -field RIL_UNSSSCODE_CLIRSUPPRESSREJECT


### -field RIL_UNSSSCODE_MAX


## -remarks
