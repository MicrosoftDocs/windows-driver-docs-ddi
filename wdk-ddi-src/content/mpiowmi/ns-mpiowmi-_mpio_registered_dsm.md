---
UID: NS:mpiowmi._MPIO_REGISTERED_DSM
title: _MPIO_REGISTERED_DSM (mpiowmi.h)
description: The MPIO_REGISTERED_DSM structure represents the top-level view of the registered DSMs on the system. To query this information, the request must be sent to the MPIO control object by using its WMI instance name.
old-location: storage\mpio_registered_dsm.htm
tech.root: storage
ms.assetid: c1be07b7-ebce-422f-83f2-890adc71655b
ms.date: 03/29/2018
ms.keywords: "*PMPIO_REGISTERED_DSM, MPIO_REGISTERED_DSM, MPIO_REGISTERED_DSM structure [Storage Devices], PMPIO_REGISTERED_DSM, PMPIO_REGISTERED_DSM structure pointer [Storage Devices], _MPIO_REGISTERED_DSM, mpiowmi/MPIO_REGISTERED_DSM, mpiowmi/PMPIO_REGISTERED_DSM, storage.mpio_registered_dsm, structs-scsibus_70ceccae-5a45-4ce1-a6de-fa86c3d82d7d.xml"
f1_keywords:
 - "mpiowmi/MPIO_REGISTERED_DSM"
req.header: mpiowmi.h
req.include-header: Mpiowmi.h
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
- mpiowmi.h
api_name:
- MPIO_REGISTERED_DSM
product:
- Windows
targetos: Windows
req.typenames: MPIO_REGISTERED_DSM, *PMPIO_REGISTERED_DSM
---

# _MPIO_REGISTERED_DSM structure


## -description


The MPIO_REGISTERED_DSM structure represents the top-level view of the registered DSMs on the system. To query this information, the request must be sent to the MPIO control object by using its WMI instance name.


## -struct-fields




### -field NumberDSMs

An unsigned 32-bitfield that specifies the number of DSMs that are registered in the system.


### -field DsmParameters

An array that returns information about each of the registered DSMs. The number of elements in the array is given by <i>NumberDSMs</i> and each element is an instance of the DSM_PARAMETERS structure.

