---
UID: NE:ntddrilapitypes.RILREGSTAT
title: RILREGSTAT (ntddrilapitypes.h)
description: This enumeration describes the RILREGSTAT.
old-location: netvista\rilregstat.htm
tech.root: netvista
ms.assetid: 53c72dbb-cf8d-4683-a440-985669265a52
ms.date: 02/16/2018
ms.keywords: RILREGSTAT, RILREGSTAT enumeration [Network Drivers Starting with Windows Vista], RIL_REGSTAT_ATTEMPTING, RIL_REGSTAT_DENIED, RIL_REGSTAT_HOME, RIL_REGSTAT_ROAMING, RIL_REGSTAT_ROAMING_INTL, RIL_REGSTAT_UNKNOWN, RIL_REGSTAT_UNREGISTERED, netvista.rilregstat, rilapitypes/RILREGSTAT, rilapitypes/RIL_REGSTAT_ATTEMPTING, rilapitypes/RIL_REGSTAT_DENIED, rilapitypes/RIL_REGSTAT_HOME, rilapitypes/RIL_REGSTAT_ROAMING, rilapitypes/RIL_REGSTAT_ROAMING_INTL, rilapitypes/RIL_REGSTAT_UNKNOWN, rilapitypes/RIL_REGSTAT_UNREGISTERED
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
- RILREGSTAT
product:
- Windows
targetos: Windows
req.typenames: RILREGSTAT
---

# RILREGSTAT enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILREGSTAT.


## -syntax


```cpp
enum RILREGSTAT  {
  RIL_REGSTAT_UNKNOWN       = 0x00000000,
  RIL_REGSTAT_UNREGISTERED  = 0x00000001,
  RIL_REGSTAT_HOME          = 0x00000002,
  RIL_REGSTAT_ATTEMPTING    = 0x00000003,
  RIL_REGSTAT_DENIED        = 0x00000004,
  RIL_REGSTAT_ROAMING       = 0x00000005,
  RIL_REGSTAT_ROAMING_INTL  = 0x00000006

};
```


## -enum-fields




### -field RIL_REGSTAT_UNKNOWN


### -field RIL_REGSTAT_UNREGISTERED


### -field RIL_REGSTAT_HOME


### -field RIL_REGSTAT_ATTEMPTING


### -field RIL_REGSTAT_DENIED


### -field RIL_REGSTAT_ROAMING


### -field RIL_REGSTAT_ROAMING_DOMESTIC


### -field RIL_REGSTAT_MAX




#### - RIL_REGSTAT_ROAMING_INTL


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>



 

 


