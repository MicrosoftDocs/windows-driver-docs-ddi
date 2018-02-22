---
UID: NS:winbio_types._WINBIO_VERSION
title: "_WINBIO_VERSION"
author: windows-driver-content
description: The WINBIO_VERSION structure describes major and minor version information for a WBDI driver.
old-location: biometric\winbio_version.htm
old-project: biometric
ms.assetid: 6a89a581-0af4-4a42-be81-fb7cb1f33bdd
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WINBIO_VERSION structure [Biometric Devices], winbio_types/WINBIO_VERSION, *PWINBIO_VERSION, WINBIO_VERSION, biometric_ref_2f55229e-601f-422c-b35c-0fb58605b273.xml, PWINBIO_VERSION, winbio_types/PWINBIO_VERSION, PWINBIO_VERSION structure pointer [Biometric Devices], _WINBIO_VERSION, biometric.winbio_version
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winbio_types.h
apiname:
-	WINBIO_VERSION
product: Windows
targetos: Windows
req.typenames: "*PWINBIO_VERSION, WINBIO_VERSION"
req.product: Windows 10 or later.
---

# _WINBIO_VERSION structure


## -description


The WINBIO_VERSION structure describes major and minor version information for a WBDI driver.


## -syntax


````
typedef struct _WINBIO_VERSION {
  DWORD MajorVersion;
  DWORD MinorVersion;
} WINBIO_VERSION, *PWINBIO_VERSION;
````


## -struct-fields




### -field MajorVersion

Identifies the major version of the driver.


### -field MinorVersion

Identifies the minor version of the driver.

