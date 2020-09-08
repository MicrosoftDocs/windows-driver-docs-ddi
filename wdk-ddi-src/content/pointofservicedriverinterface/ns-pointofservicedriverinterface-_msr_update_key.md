---
UID: NS:pointofservicedriverinterface._MSR_UPDATE_KEY
title: _MSR_UPDATE_KEY (pointofservicedriverinterface.h)
description: This structure contains the information necessary to set a new encryption key.
old-location: pos\msr_update_key.htm
tech.root: pos
ms.assetid: 8d7f85d4-af10-4ae5-a891-18dd41192c6a
ms.date: 02/23/2018
keywords: ["MSR_UPDATE_KEY structure"]
ms.keywords: "*PMSR_UPDATE_KEY, MSR_UPDATE_KEY, MSR_UPDATE_KEY structure, PMSR_UPDATE_KEY, PMSR_UPDATE_KEY structure pointer, _MSR_UPDATE_KEY, pointofservicedriverinterface/MSR_UPDATE_KEY, pointofservicedriverinterface/PMSR_UPDATE_KEY, pos.msr_update_key"
req.header: pointofservicedriverinterface.h
req.include-header: PointOfServiceDriverInterface.h
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
req.typenames: MSR_UPDATE_KEY, *PMSR_UPDATE_KEY
f1_keywords:
 - _MSR_UPDATE_KEY
 - pointofservicedriverinterface/_MSR_UPDATE_KEY
 - PMSR_UPDATE_KEY
 - pointofservicedriverinterface/PMSR_UPDATE_KEY
 - MSR_UPDATE_KEY
 - pointofservicedriverinterface/MSR_UPDATE_KEY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - PointOfServiceDriverInterface.h
api_name:
 - MSR_UPDATE_KEY
---

# _MSR_UPDATE_KEY structure


## -description

This structure contains the information necessary to set a new encryption key.

## -struct-fields

### -field KeyLength

Length, in bytes, of the key stored in **Key[MSR_KEY_SIZE]**.

### -field KeyNameLength

Length, in bytes, of the key name stored in **KeyName[MSR_KEY_SIZE]**.

### -field Key

The new encryption key.

### -field KeyName

 




#### - char KeyName

The name of the new encryption key.

