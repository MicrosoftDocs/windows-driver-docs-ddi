---
UID: NE:ucmtypes._UCM_TYPEC_CURRENT
title: "_UCM_TYPEC_CURRENT"
author: windows-driver-content
description: Defines different Type-C current levels, as defined in the Type-C specification.
old-location: buses\ucm_type_c_current.htm
tech.root: usbref
ms.assetid: 5A603C0E-BBB8-4909-B7B0-EAADF428CB5F
ms.date: 5/7/2018
ms.keywords: UCM_TYPEC_CURRENT, UCM_TYPEC_CURRENT enumeration [Buses], UcmTypeCCurrent1500mA, UcmTypeCCurrent3000mA, UcmTypeCCurrentDefaultUsb, UcmTypeCCurrentInvalid, _UCM_TYPEC_CURRENT, buses.ucm_type_c_current, ucmtypes/UCM_TYPEC_CURRENT, ucmtypes/UcmTypeCCurrent1500mA, ucmtypes/UcmTypeCCurrent3000mA, ucmtypes/UcmTypeCCurrentDefaultUsb, ucmtypes/UcmTypeCCurrentInvalid
ms.topic: enum
req.header: ucmtypes.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
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
-	Ucmtypes.h
api_name:
-	UCM_TYPEC_CURRENT
product:
- Windows
targetos: Windows
req.typenames: UCM_TYPEC_CURRENT
---

# _UCM_TYPEC_CURRENT enumeration


## -description


Defines different Type-C current levels, as defined in the Type-C specification.


## -enum-fields




### -field UcmTypeCCurrentInvalid

Indicates the power sourcing current state is invalid.


### -field UcmTypeCCurrentDefaultUsb

Indicates the power sourcing current is the default USB current.


### -field UcmTypeCCurrent1500mA

Indicates the power sourcing current is 1500 mA.


### -field UcmTypeCCurrent3000mA

Indicates the power sourcing current is 3000 mA.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt187915">UcmConnectorTypeCAttach</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187916">UcmConnectorTypeCCurrentAdChanged</a>
 

 

