---
UID: NE:ntddrilapitypes.RILUICCFILELOCKSTATUSPARAMMASK
title: RILUICCFILELOCKSTATUSPARAMMASK (ntddrilapitypes.h)
description: This enumeration describes the RILUICCFILELOCKSTATUSPARAMMASK.
old-location: netvista\riluiccfilelockstatusparammask.htm
tech.root: netvista
ms.assetid: 341e11bb-957b-4745-9892-f1274ff97f44
ms.date: 02/16/2018
ms.keywords: RILUICCFILELOCKSTATUSPARAMMASK, RILUICCFILELOCKSTATUSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_UFLS_ACCESSCONDITION, RIL_PARAM_UFLS_ALL, RIL_PARAM_UFLS_PINREFERENCE, netvista.riluiccfilelockstatusparammask, rilapitypes/RILUICCFILELOCKSTATUSPARAMMASK, rilapitypes/RIL_PARAM_UFLS_ACCESSCONDITION, rilapitypes/RIL_PARAM_UFLS_ALL, rilapitypes/RIL_PARAM_UFLS_PINREFERENCE
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rilapitypes.h
api_name:
- RILUICCFILELOCKSTATUSPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILUICCFILELOCKSTATUSPARAMMASK
---

# RILUICCFILELOCKSTATUSPARAMMASK enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCFILELOCKSTATUSPARAMMASK.


## -syntax


```cpp
enum RILUICCFILELOCKSTATUSPARAMMASK {
  RIL_PARAM_UFLS_ACCESSCONDITION  = 0x00000001,
  RIL_PARAM_UFLS_PINREFERENCE     = 0x00000002,
  RIL_PARAM_UFLS_ALL              = 0x00000003

};
```


## -enum-fields




### -field RIL_PARAM_UFLS_ACCESSCONDITION


### -field RIL_PARAM_UFLS_PINREFERENCE


### -field RIL_PARAM_UFLS_ALL


## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/cellular/dn946509(v=vs.85)">Cellular COM enumerations</a>



 

 


