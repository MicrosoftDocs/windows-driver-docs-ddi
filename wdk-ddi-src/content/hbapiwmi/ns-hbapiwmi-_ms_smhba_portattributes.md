---
UID: NS:hbapiwmi._MS_SMHBA_PORTATTRIBUTES
title: "_MS_SMHBA_PORTATTRIBUTES"
author: windows-driver-content
description: The MS_SMHBA_PORTATTRIBUTES structure is used to report the port information.
old-location: storage\ms_smhba_portattributes.htm
old-project: storage
ms.assetid: ce967b15-723f-4ab7-8a79-8234291d1950
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PMS_SMHBA_PORTATTRIBUTES, ,, A, B, E, H, I, M, MS_SMHBA_PORTATTRIBUTES, MS_SMHBA_PORTATTRIBUTES structure [Storage Devices], O, P, PMS_SMHBA_PORTATTRIBUTES, PMS_SMHBA_PORTATTRIBUTES structure pointer [Storage Devices], R, S, T, U, _, _MS_SMHBA_PORTATTRIBUTES, hbapiwmi/MS_SMHBA_PORTATTRIBUTES, hbapiwmi/PMS_SMHBA_PORTATTRIBUTES, storage.ms_smhba_portattributes, structs-Fibre_66af1ae7-5db4-4dd3-bacc-0665dd757660.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hbapiwmi.h
apiname:
-	MS_SMHBA_PORTATTRIBUTES
product: Windows
targetos: Windows
req.typenames: MS_SMHBA_PORTATTRIBUTES, *PMS_SMHBA_PORTATTRIBUTES
---

# _MS_SMHBA_PORTATTRIBUTES structure


## -description


The MS_SMHBA_PORTATTRIBUTES structure is used to report the port information.


## -syntax


````
typedef struct _MS_SMHBA_PORTATTRIBUTES {
  ULONG     PortType;
  ULONG     PortState;
  ULONG     PortSpecificAttributesSize;
  WCHAR     OSDeviceName[256 + 1];
  ULONGLONG Reserved;
  UCHAR     PortSpecificAttributes[1];
} MS_SMHBA_PORTATTRIBUTES, *PMS_SMHBA_PORTATTRIBUTES;
````


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

