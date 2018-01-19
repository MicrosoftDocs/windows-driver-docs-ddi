---
UID: NE:rilapitypes.RILCALLFORWARDINGSETTINGSREASON
title: RILCALLFORWARDINGSETTINGSREASON
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallforwardingsettingsreason_2.htm
old-project: netvista
ms.assetid: 765c34f7-c1c3-4579-b813-0c9845b3fabb
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLFORWARDINGSETTINGSREASON, RILCALLFORWARDINGSETTINGSREASON
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILCALLFORWARDINGSETTINGSREASON
req.alt-loc: rilapitypes.h
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
req.typenames: RILCALLFORWARDINGSETTINGSREASON
req.product: Windows 10 or later.
---

# RILCALLFORWARDINGSETTINGSREASON enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef enum _RILCALLFORWARDINGSETTINGSREASON { 
  RIL_FWDREASON_MOBILEBUSY,
  RIL_FWDREASON_NOREPLY,
  RIL_FWDREASON_UNREACHABLE,
  RIL_FWDREASON_ALLFORWARDING,
  RIL_FWDREASON_ALLCONDITIONAL,
  RIL_FWDREASON_MAX
} RILCALLFORWARDINGSETTINGSREASON;
````


## -enum-fields

### -field RIL_FWDREASON_MOBILEBUSY


### -field RIL_FWDREASON_NOREPLY


### -field RIL_FWDREASON_UNREACHABLE


### -field RIL_FWDREASON_ALLFORWARDING


### -field RIL_FWDREASON_ALLCONDITIONAL


### -field RIL_FWDREASON_MAX


## -remarks
