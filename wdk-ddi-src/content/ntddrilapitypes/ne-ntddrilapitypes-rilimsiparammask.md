---
UID: NE:ntddrilapitypes.RILIMSIPARAMMASK
title: RILIMSIPARAMMASK
author: windows-driver-content
description: This enumeration describes the RILIMSIPARAMMASK.
old-location: netvista\rilimsiparammask.htm
tech.root: netvista
ms.assetid: 8fe1ecda-4b2f-4a6f-b02c-7e50630614eb
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILIMSIPARAMMASK, RILIMSIPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_IMSI_ALL, RIL_PARAM_IMSI_IMSI, RIL_PARAM_IMSI_MCC, RIL_PARAM_IMSI_MNC, netvista.rilimsiparammask, rilapitypes/RILIMSIPARAMMASK, rilapitypes/RIL_PARAM_IMSI_ALL, rilapitypes/RIL_PARAM_IMSI_IMSI, rilapitypes/RIL_PARAM_IMSI_MCC, rilapitypes/RIL_PARAM_IMSI_MNC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h, Ntddrilapitypes.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILIMSIPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILIMSIPARAMMASK
---

# RILIMSIPARAMMASK enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILIMSIPARAMMASK.




## -syntax


```
enum RILIMSIPARAMMASK {
  RIL_PARAM_IMSI_IMSI  = 0x00000001,
  RIL_PARAM_IMSI_MCC   = 0x00000002,
  RIL_PARAM_IMSI_MNC   = 0x00000004,
  RIL_PARAM_IMSI_ALL   = 0x00000007

};
```


## -enum-fields




### -field RIL_PARAM_IMSI_IMSI


### -field RIL_PARAM_IMSI_MCC


### -field RIL_PARAM_IMSI_MNC


### -field RIL_PARAM_IMSI_ALL


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 


