---
UID: NS:hbapiwmi._MS_SMHBA_PORTATTRIBUTES
title: _MS_SMHBA_PORTATTRIBUTES (hbapiwmi.h)
description: The MS_SMHBA_PORTATTRIBUTES structure is used to report the port information.
old-location: storage\ms_smhba_portattributes.htm
tech.root: storage
ms.assetid: ce967b15-723f-4ab7-8a79-8234291d1950
ms.date: 03/29/2018
keywords: ["_MS_SMHBA_PORTATTRIBUTES structure"]
ms.keywords: "*PMS_SMHBA_PORTATTRIBUTES, MS_SMHBA_PORTATTRIBUTES, MS_SMHBA_PORTATTRIBUTES structure [Storage Devices], PMS_SMHBA_PORTATTRIBUTES, PMS_SMHBA_PORTATTRIBUTES structure pointer [Storage Devices], _MS_SMHBA_PORTATTRIBUTES, hbapiwmi/MS_SMHBA_PORTATTRIBUTES, hbapiwmi/PMS_SMHBA_PORTATTRIBUTES, storage.ms_smhba_portattributes, structs-Fibre_66af1ae7-5db4-4dd3-bacc-0665dd757660.xml"
f1_keywords:
 - "hbapiwmi/MS_SMHBA_PORTATTRIBUTES"
 - "MS_SMHBA_PORTATTRIBUTES"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
- hbapiwmi.h
api_name:
- MS_SMHBA_PORTATTRIBUTES
product:
- Windows
targetos: Windows
req.typenames: MS_SMHBA_PORTATTRIBUTES, *PMS_SMHBA_PORTATTRIBUTES
---

# _MS_SMHBA_PORTATTRIBUTES structure


## -description


The MS_SMHBA_PORTATTRIBUTES structure is used to report the port information.


## -struct-fields




### -field PortType

An integer that indicates the port type of the SMHBA port.


### -field PortState

An integer that indicates the current state of the SMHBA port.


### -field PortSpecificAttributesSize


### -field OSDeviceName

A nonpersistent operating system target name, for example "\Device\HarddiskVolume1".


### -field Reserved


### -field PortSpecificAttributes

