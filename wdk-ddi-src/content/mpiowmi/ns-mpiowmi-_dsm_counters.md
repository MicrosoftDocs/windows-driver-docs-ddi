---
UID: NS:mpiowmi._DSM_COUNTERS
title: _DSM_COUNTERS (mpiowmi.h)
description: The DSM_COUNTERS structure holds the various timer counters that are applicable to all LUNs that are controlled by the DSM.
old-location: storage\dsm_counters.htm
tech.root: storage
ms.assetid: 3202aec4-d95e-4162-86a1-17595ed2a5b5
ms.date: 03/29/2018
ms.keywords: "*PDSM_COUNTERS, DSM_COUNTERS, DSM_COUNTERS structure [Storage Devices], PDSM_COUNTERS, PDSM_COUNTERS structure pointer [Storage Devices], _DSM_COUNTERS, mpiowmi/DSM_COUNTERS, mpiowmi/PDSM_COUNTERS, storage.dsm_counters, structs-scsibus_bfb9b1ff-6274-47b9-b817-254428b02f17.xml"
f1_keywords:
 - "mpiowmi/DSM_COUNTERS"
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
- DSM_COUNTERS
product:
- Windows
targetos: Windows
req.typenames: DSM_COUNTERS, *PDSM_COUNTERS
---

# _DSM_COUNTERS structure


## -description


The DSM_COUNTERS structure holds the various timer counters that are applicable to all LUNs that are controlled by the DSM.


## -struct-fields




### -field PathVerifyEnabled

An unsigned 32-bitfield that is used as a flag. This field indicates if path verification must be performed by MPIO periodically on all paths that expose devices that are controlled by this particular DSM.


### -field PathVerificationPeriod

An unsigned 32-bitfield that is used to indicate the periodicity (in seconds) with which MPIO has been requested to perform path verification. This field is only honored if <i>PathVerifyEnabled</i> is <b>TRUE</b>.


### -field PDORemovePeriod

An unsigned 32-bitfield that controls the amount of time (in seconds) that the pseudo-LUN will continue to remain in system memory, even after losing all its path information.


### -field RetryCount

An unsigned 32-bitfield that specifies the number of times a failed I/O will be retried.


### -field RetryInterval

An unsigned 32-bitfield that specifies the interval of time (in seconds) after which a failed request is retried.


### -field Reserved32

Should be zero.


### -field Reserved64

Should be zero.

