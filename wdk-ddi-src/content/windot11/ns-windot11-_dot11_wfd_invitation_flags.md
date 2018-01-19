---
UID: NS:windot11._DOT11_WFD_INVITATION_FLAGS
title: _DOT11_WFD_INVITATION_FLAGS
author: windows-driver-content
description: The DOT11_WFD_INVITATION_FLAGS structure represents the Invitation Attributes used during the Invitation procedure.
old-location: netvista\dot11_wfd_invitation_flags.htm
old-project: netvista
ms.assetid: 9743FF37-0E8A-499F-AADB-9CD7BDC381E0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DOT11_WFD_INVITATION_FLAGS, DOT11_WFD_INVITATION_FLAGS, *PDOT11_WFD_INVITATION_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with   Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_WFD_INVITATION_FLAGS
req.alt-loc: Windot11.h
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
req.typenames: DOT11_WFD_INVITATION_FLAGS, *PDOT11_WFD_INVITATION_FLAGS
req.product: Windows 10 or later.
---

# _DOT11_WFD_INVITATION_FLAGS structure



## -description

## -syntax

````
typedef struct _DOT11_WFD_INVITATION_FLAGS {
  UCHAR InvitationType:1;
  UCHAR Reserved:7;
} DOT11_WFD_INVITATION_FLAGS, *PDOT11_WFD_INVITATION_FLAGS;
````


## -struct-fields

### -field InvitationType:1

The type of group invitation. The invitation types have the following meanings.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field Join
### -field 0

</td>
<td width="60%">
An invitiation to join an active group.

</td>
</tr>
<tr>

### -field Reinvoke
### -field 1

</td>
<td width="60%">
The invitation is reinvoked.

</td>
</tr>
</table>
 


### -field Reserved:7

Reserved.


## -remarks
