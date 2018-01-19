---
UID: NS:hbapiwmi._MS_SMHBA_PORTATTRIBUTES
title: _MS_SMHBA_PORTATTRIBUTES
author: windows-driver-content
description: The MS_SMHBA_PORTATTRIBUTES structure is used to report the port information.
old-location: storage\ms_smhba_portattributes.htm
old-project: storage
ms.assetid: ce967b15-723f-4ab7-8a79-8234291d1950
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _MS_SMHBA_PORTATTRIBUTES, *PMS_SMHBA_PORTATTRIBUTES, MS_SMHBA_PORTATTRIBUTES
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
req.alt-api: MS_SMHBA_PORTATTRIBUTES
req.alt-loc: hbapiwmi.h
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
req.typenames: *PMS_SMHBA_PORTATTRIBUTES, MS_SMHBA_PORTATTRIBUTES
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


## -remarks
