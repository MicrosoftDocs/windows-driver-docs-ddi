---
UID: NS:winbio_types._WINBIO_REGISTERED_FORMAT
title: _WINBIO_REGISTERED_FORMAT (winbio_types.h)
description: The WINBIO_REGISTERED_FORMAT structure specifies a biometric data format.
old-location: biometric\winbio_registered_format.htm
tech.root: biometric
ms.assetid: 70591143-f429-4a6e-8f2a-cc1082f40f6e
ms.date: 02/20/2018
ms.keywords: "*PWINBIO_REGISTERED_FORMAT, PWINBIO_REGISTERED_FORMAT, PWINBIO_REGISTERED_FORMAT structure pointer [Biometric Devices], WINBIO_REGISTERED_FORMAT, WINBIO_REGISTERED_FORMAT structure [Biometric Devices], _WINBIO_REGISTERED_FORMAT, biometric.winbio_registered_format, biometric_ref_824bd2c9-98a7-4967-8416-82aadd8ec6ed.xml, winbio_types/PWINBIO_REGISTERED_FORMAT, winbio_types/WINBIO_REGISTERED_FORMAT"
ms.topic: struct
req.header: winbio_types.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	winbio_types.h
api_name:
-	WINBIO_REGISTERED_FORMAT
product:
- Windows
targetos: Windows
req.typenames: WINBIO_REGISTERED_FORMAT, *PWINBIO_REGISTERED_FORMAT
---

# _WINBIO_REGISTERED_FORMAT structure


## -description


The WINBIO_REGISTERED_FORMAT structure specifies a biometric data format.


## -struct-fields




### -field Owner

Specifies format owner.


### -field Type

Specifies format type.


## -remarks

For Windows, the format owner is defined as follows:

```cpp
#define WINBIO_ANSI_381_FORMAT_OWNER    ((USHORT)0x001B)    // INCITS Technical Committee M1
```

The Type for the standard Windows fingerprint format is:

```cpp
#define WINBIO_ANSI_381_FORMAT_TYPE     ((USHORT)0x0401)    // ANSI-381
```

WBDI drivers for fingerprint sensors must support the Owner and Type for the Windows fingerprint data format. The Windows Biometric Service (WBS) verifies that a sensor minimally supports the Windows fingerprint raw data format.  Windows defines this standard raw data format to allow ISVs to write engine adapters that can take input from any sensor.  Each engine should have a capability to support at least this format, but it can specify a different format as a preferred raw format.

For information about formats for other types of sensors, see [Client Application Constants](https://docs.microsoft.com/windows/win32/secbiomet/client-application-constants).

No format owner or type are defined as follows:

```cpp
#define WINBIO_NO_FORMAT_OWNER_AVAILABLE    ((USHORT)0)
#define WINBIO_NO_FORMAT_TYPE_AVAILABLE     ((USHORT)0)
```

