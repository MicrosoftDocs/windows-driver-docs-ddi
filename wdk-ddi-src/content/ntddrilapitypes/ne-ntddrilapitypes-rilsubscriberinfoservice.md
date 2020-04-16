---
UID: NE:ntddrilapitypes.RILSUBSCRIBERINFOSERVICE
title: RILSUBSCRIBERINFOSERVICE (ntddrilapitypes.h)
description: This enumeration describes the RILSUBSCRIBERINFOSERVICE.
old-location: netvista\rilsubscriberinfoservice.htm
tech.root: netvista
ms.assetid: 9dcdfbcc-bab8-4621-993b-e64106d0457e
ms.date: 02/16/2018
keywords: ["RILSUBSCRIBERINFOSERVICE enumeration"]
ms.keywords: RILSUBSCRIBERINFOSERVICE, RILSUBSCRIBERINFOSERVICE enumeration [Network Drivers Starting with Windows Vista], RIL_SERVICE_FAX, RIL_SERVICE_OTHER, RIL_SERVICE_UNKNOWN, RIL_SERVICE_VOICE, netvista.rilsubscriberinfoservice, rilapitypes/RILSUBSCRIBERINFOSERVICE, rilapitypes/RIL_SERVICE_FAX, rilapitypes/RIL_SERVICE_OTHER, rilapitypes/RIL_SERVICE_UNKNOWN, rilapitypes/RIL_SERVICE_VOICE
f1_keywords:
 - "ntddrilapitypes/RILSUBSCRIBERINFOSERVICE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rilapitypes.h
api_name:
- RILSUBSCRIBERINFOSERVICE
product:
- Windows
targetos: Windows
req.typenames: RILSUBSCRIBERINFOSERVICE
---

# RILSUBSCRIBERINFOSERVICE enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILSUBSCRIBERINFOSERVICE.


## -syntax


```cpp
enum RILSUBSCRIBERINFOSERVICE {
  RIL_SERVICE_UNKNOWN  = 0x01,
  RIL_SERVICE_VOICE    = 0x02,
  RIL_SERVICE_FAX      = 0x03,
  RIL_SERVICE_OTHER    = 0x04

};
```


## -enum-fields




### -field RIL_SERVICE_UNKNOWN


### -field RIL_SERVICE_VOICE


### -field RIL_SERVICE_FAX


### -field RIL_SERVICE_OTHER


### -field RIL_SERVICE_MAX




## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/cellular/dn946511(v=vs.85)">Cellular COM structures</a>



 

 


