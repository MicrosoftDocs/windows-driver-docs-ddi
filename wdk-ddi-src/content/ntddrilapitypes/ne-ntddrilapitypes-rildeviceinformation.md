---
UID: NE:ntddrilapitypes.RILDEVICEINFORMATION
title: RILDEVICEINFORMATION
author: windows-driver-content
description: This enumeration describes the RILDEVICEINFORMATION.
old-location: netvista\rildeviceinformation.htm
tech.root: netvista
ms.assetid: 1abba51c-1db9-4424-aa11-64d3fd116a79
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILDEVICEINFORMATION, RILDEVICEINFORMATION enumeration [Network Drivers Starting with Windows Vista], RIL_DEVICEINFO_ARG_LARGEST, RIL_DEVICEINFO_ARG_SMALLEST, RIL_DEVICEINFO_MANUFACTURER, RIL_DEVICEINFO_MODEL, RIL_DEVICEINFO_REVISION, RIL_DEVICEINFO_SERIALNUMBER_CDMA, RIL_DEVICEINFO_SERIALNUMBER_GW, netvista.rildeviceinformation, rilapitypes/RILDEVICEINFORMATION, rilapitypes/RIL_DEVICEINFO_ARG_LARGEST, rilapitypes/RIL_DEVICEINFO_ARG_SMALLEST, rilapitypes/RIL_DEVICEINFO_MANUFACTURER, rilapitypes/RIL_DEVICEINFO_MODEL, rilapitypes/RIL_DEVICEINFO_REVISION, rilapitypes/RIL_DEVICEINFO_SERIALNUMBER_CDMA, rilapitypes/RIL_DEVICEINFO_SERIALNUMBER_GW
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
-	RILDEVICEINFORMATION
product:
- Windows
targetos: Windows
req.typenames: RILDEVICEINFORMATION
---

# RILDEVICEINFORMATION enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILDEVICEINFORMATION.


## -syntax


```cpp
enum RILDEVICEINFORMATION {
  RIL_DEVICEINFO_MANUFACTURER       = 0x01,
  RIL_DEVICEINFO_MODEL              = 0x02,
  RIL_DEVICEINFO_REVISION           = 0x03,
  RIL_DEVICEINFO_SERIALNUMBER_GW    = 0x04,
  RIL_DEVICEINFO_SERIALNUMBER_CDMA  = 0x05,
  RIL_DEVICEINFO_ARG_SMALLEST       = RIL_DEVICEINFO_MANUFACTURER,
  RIL_DEVICEINFO_ARG_LARGEST        = RIL_DEVICEINFO_SERIALNUMBER_CDMA

};
```


## -enum-fields




### -field RIL_DEVICEINFO_MANUFACTURER


### -field RIL_DEVICEINFO_MODEL


### -field RIL_DEVICEINFO_REVISION


### -field RIL_DEVICEINFO_SERIALNUMBER_GW


### -field RIL_DEVICEINFO_SERIALNUMBER_CDMA


### -field RIL_DEVICEINFO_ARG_SMALLEST


### -field RIL_DEVICEINFO_ARG_LARGEST


### -field RIL_DEVICEINFO_MIN


### -field RIL_DEVICEINFO_MAX




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 


