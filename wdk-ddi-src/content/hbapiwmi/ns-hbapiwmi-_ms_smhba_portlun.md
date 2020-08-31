---
UID: NS:hbapiwmi._MS_SMHBA_PORTLUN
title: _MS_SMHBA_PORTLUN (hbapiwmi.h)
description: The MS_SMHBA_PORTLUN structure reports target LUN information that is associated with a port.
old-location: storage\ms_smhba_portlun.htm
tech.root: storage
ms.assetid: cf62685f-7b4d-4671-a755-d59a593bf5d6
ms.date: 03/29/2018
keywords: ["MS_SMHBA_PORTLUN structure"]
ms.keywords: "*PMS_SMHBA_PORTLUN, MS_SMHBA_PORTLUN, MS_SMHBA_PORTLUN structure [Storage Devices], PMS_SMHBA_PORTLUN, PMS_SMHBA_PORTLUN structure pointer [Storage Devices], _MS_SMHBA_PORTLUN, hbapiwmi/MS_SMHBA_PORTLUN, hbapiwmi/PMS_SMHBA_PORTLUN, storage.ms_smhba_portlun, structs-Fibre_a0363ae3-80ce-4efd-8409-826d1810190c.xml"
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
targetos: Windows
req.typenames: MS_SMHBA_PORTLUN, *PMS_SMHBA_PORTLUN
f1_keywords:
 - _MS_SMHBA_PORTLUN
 - hbapiwmi/_MS_SMHBA_PORTLUN
 - PMS_SMHBA_PORTLUN
 - hbapiwmi/PMS_SMHBA_PORTLUN
 - MS_SMHBA_PORTLUN
 - hbapiwmi/MS_SMHBA_PORTLUN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - MS_SMHBA_PORTLUN
---

# _MS_SMHBA_PORTLUN structure


## -description

The MS_SMHBA_PORTLUN structure reports target LUN information that is associated with a port.

## -struct-fields

### -field PortWWN

The worldwide name of the local port whose events the WMI client will receive.

### -field domainPortWWN

A worldwide name that specifies the SAS domain worldwide name of the local port.

### -field TargetLun

The target LUN number.

