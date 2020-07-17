---
UID: NS:hbapiwmi._SM_GetTargetMapping_IN
title: _SM_GetTargetMapping_IN (hbapiwmi.h)
description: The SM_GetTargetMapping_IN structure is used to provide input parameters to the SM_GetTargetMapping method.
old-location: storage\sm_gettargetmapping_in.htm
tech.root: storage
ms.assetid: d6f73582-5eaf-452f-ad5a-cdf5ab99d809
ms.date: 03/29/2018
keywords: ["_SM_GetTargetMapping_IN structure"]
ms.keywords: "*PSM_GetTargetMapping_IN, PSM_GetTargetMapping_IN, PSM_GetTargetMapping_IN structure pointer [Storage Devices], SM_GetTargetMapping_IN, SM_GetTargetMapping_IN structure [Storage Devices], _SM_GetTargetMapping_IN, hbapiwmi/PSM_GetTargetMapping_IN, hbapiwmi/SM_GetTargetMapping_IN, storage.sm_gettargetmapping_in, structs-Fibre_0109f5f0-dd0c-4a30-8b0a-aa33a54b5a61.xml"
f1_keywords:
 - "hbapiwmi/SM_GetTargetMapping_IN"
 - "SM_GetTargetMapping_IN"
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
- SM_GetTargetMapping_IN
product:
- Windows
targetos: Windows
req.typenames: SM_GetTargetMapping_IN, *PSM_GetTargetMapping_IN
---

# _SM_GetTargetMapping_IN structure


## -description


The SM_GetTargetMapping_IN structure is used to provide input parameters to the SM_GetTargetMapping method.


## -struct-fields




### -field HbaPortWWN

The worldwide name (WWN) of the local port whose events the WMI client will receive.


### -field DomainPortWWN

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.


### -field InEntryCount

The number of persistent bindings that are associated with the HBA.


## -remarks



The WMI tool suite generates a declaration of the SM_GetTargetMapping_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.



