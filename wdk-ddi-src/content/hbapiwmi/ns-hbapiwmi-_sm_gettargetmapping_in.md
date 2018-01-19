---
UID: NS:hbapiwmi._SM_GetTargetMapping_IN
title: _SM_GetTargetMapping_IN
author: windows-driver-content
description: The SM_GetTargetMapping_IN structure is used to provide input parameters to the SM_GetTargetMapping method.
old-location: storage\sm_gettargetmapping_in.htm
old-project: storage
ms.assetid: d6f73582-5eaf-452f-ad5a-cdf5ab99d809
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SM_GetTargetMapping_IN, *PSM_GetTargetMapping_IN, SM_GetTargetMapping_IN
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
req.alt-api: SM_GetTargetMapping_IN
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
req.typenames: *PSM_GetTargetMapping_IN, SM_GetTargetMapping_IN
---

# _SM_GetTargetMapping_IN structure



## -description
The SM_GetTargetMapping_IN structure is used to provide input parameters to the SM_GetTargetMapping method.



## -syntax

````
typedef struct _SM_GetTargetMapping_IN {
  UCHAR HbaPortWWN[8];
  UCHAR DomainPortWWN[8];
  ULONG InEntryCount;
} SM_GetTargetMapping_IN, *PSM_GetTargetMapping_IN;
````


## -struct-fields

### -field HbaPortWWN

The worldwide name (WWN) of the local port whose events the WMI client will receive.


### -field DomainPortWWN

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.


### -field InEntryCount

The number of persistent bindings that are associated with the HBA.


## -remarks
The WMI tool suite generates a declaration of the SM_GetTargetMapping_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.</p>