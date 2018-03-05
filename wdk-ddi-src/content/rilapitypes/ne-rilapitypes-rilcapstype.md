---
UID: NE:rilapitypes.RILCAPSTYPE
title: RILCAPSTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcapstype_2.htm
old-project: netvista
ms.assetid: 492436da-9d6f-462b-9c4d-4466cb2f78f6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILCAPSTYPE, RILCAPSTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_CAPSTYPE_ARG_LARGEST, RIL_CAPSTYPE_ARG_SMALLEST, RIL_CAPSTYPE_CALLSUPPORT, RIL_CAPSTYPE_MAX, RIL_CAPSTYPE_NITZNOTIFICATION, RIL_CAPSTYPE_PBMAXREAD, RIL_CAPSTYPE_PBSTORELOCATIONS, RIL_CAPSTYPE_PERSOLOCKPWDLENGTH, RIL_CAPSTYPE_RADIOCONFIGURATIONS, RIL_CAPSTYPE_SIGNALQUALITYIMPLEMENTATION, RIL_CAPSTYPE_SMSSUPPORT, netvista.rilcapstype_2, rilapitypes/RILCAPSTYPE, rilapitypes/RIL_CAPSTYPE_ARG_LARGEST, rilapitypes/RIL_CAPSTYPE_ARG_SMALLEST, rilapitypes/RIL_CAPSTYPE_CALLSUPPORT, rilapitypes/RIL_CAPSTYPE_MAX, rilapitypes/RIL_CAPSTYPE_NITZNOTIFICATION, rilapitypes/RIL_CAPSTYPE_PBMAXREAD, rilapitypes/RIL_CAPSTYPE_PBSTORELOCATIONS, rilapitypes/RIL_CAPSTYPE_PERSOLOCKPWDLENGTH, rilapitypes/RIL_CAPSTYPE_RADIOCONFIGURATIONS, rilapitypes/RIL_CAPSTYPE_SIGNALQUALITYIMPLEMENTATION, rilapitypes/RIL_CAPSTYPE_SMSSUPPORT
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILCAPSTYPE
product: Windows
targetos: Windows
req.typenames: RILCAPSTYPE
req.product: Windows 10 or later.
---

# RILCAPSTYPE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILCAPSTYPE { 
  RIL_CAPSTYPE_PERSOLOCKPWDLENGTH,
  RIL_CAPSTYPE_PBMAXREAD,
  RIL_CAPSTYPE_PBSTORELOCATIONS,
  RIL_CAPSTYPE_RADIOCONFIGURATIONS,
  RIL_CAPSTYPE_SIGNALQUALITYIMPLEMENTATION,
  RIL_CAPSTYPE_NITZNOTIFICATION,
  RIL_CAPSTYPE_CALLSUPPORT,
  RIL_CAPSTYPE_SMSSUPPORT,
  RIL_CAPSTYPE_ARG_SMALLEST,
  RIL_CAPSTYPE_ARG_LARGEST,
  RIL_CAPSTYPE_MAX
} RILCAPSTYPE;
````


## -enum-fields




### -field RIL_CAPSTYPE_PERSOLOCKSUPPORT


### -field RIL_CAPSTYPE_PERSOLOCKPWDLENGTH


### -field RIL_CAPSTYPE_PBMAXREAD


### -field RIL_CAPSTYPE_PBSTORELOCATIONS


### -field RIL_CAPSTYPE_RADIOCONFIGURATIONS


### -field RIL_CAPSTYPE_SIGNALQUALITYIMPLEMENTATION


### -field RIL_CAPSTYPE_NITZNOTIFICATION


### -field RIL_CAPSTYPE_CALLSUPPORT


### -field RIL_CAPSTYPE_SMSSUPPORT


### -field RIL_CAPSTYPE_ARG_SMALLEST


### -field RIL_CAPSTYPE_ARG_LARGEST


### -field RIL_CAPSTYPE_MAX

