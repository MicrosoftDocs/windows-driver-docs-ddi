---
UID: NE:rilapitypes.RILNOTIFICATIONFILTERMASK
title: RILNOTIFICATIONFILTERMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnotificationfiltermask_2.htm
old-project: netvista
ms.assetid: 00d083af-f2c1-4ad5-803a-5981ed70035f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_NFS_LOCATIONUPDATE, netvista.rilnotificationfiltermask_2, rilapitypes/RIL_NFS_REGSTATUS_RATKIND, rilapitypes/RIL_NFS_ALL, RIL_NFS_REGSTATUS_RATKIND, RIL_NFS_SIGNALQUALITY, rilapitypes/RILNOTIFICATIONFILTERMASK, rilapitypes/RIL_NFS_SIGNALQUALITY, RILNOTIFICATIONFILTERMASK, RILNOTIFICATIONFILTERMASK enumeration [Network Drivers Starting with Windows Vista], RIL_NFS_ALL, RIL_NFS_LOCATIONUPDATE
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILNOTIFICATIONFILTERMASK
product: Windows
targetos: Windows
req.typenames: RILNOTIFICATIONFILTERMASK
req.product: Windows 10 or later.
---

# RILNOTIFICATIONFILTERMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILNOTIFICATIONFILTERMASK { 
  RIL_NFS_SIGNALQUALITY,
  RIL_NFS_REGSTATUS_RATKIND,
  RIL_NFS_LOCATIONUPDATE,
  RIL_NFS_ALL
} RILNOTIFICATIONFILTERMASK;
````


## -enum-fields




### -field RIL_NFS_NONE



### -field RIL_NFS_SIGNALQUALITY



### -field RIL_NFS_REGSTATUS_RATKIND



### -field RIL_NFS_LOCATIONUPDATE



### -field RIL_NFS_ALL


