---
UID: NS:mpiowmi._DSM_PARAMETERS
title: "_DSM_PARAMETERS"
author: windows-driver-content
description: The DSM_PARAMETERS structure holds the DSM version and timer counters information.
old-location: storage\dsm_parameters.htm
tech.root: storage
ms.assetid: 948331f1-1398-4e6e-85cb-27bbbd79630e
ms.date: 03/29/2018
ms.keywords: "*PDSM_PARAMETERS, DSM_PARAMETERS, DSM_PARAMETERS structure [Storage Devices], PDSM_PARAMETERS, PDSM_PARAMETERS structure pointer [Storage Devices], _DSM_PARAMETERS, mpiowmi/DSM_PARAMETERS, mpiowmi/PDSM_PARAMETERS, storage.dsm_parameters, structs-scsibus_e2e8b9f3-6452-4244-b9df-7301ce461764.xml"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mpiowmi.h
api_name:
-	DSM_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DSM_PARAMETERS, *PDSM_PARAMETERS
---

# _DSM_PARAMETERS structure


## -description


The DSM_PARAMETERS structure holds the DSM version and timer counters information.


## -struct-fields




### -field DsmName

A string field of maximum length 63 characters that returns the friendly name of the DSM.


### -field DsmContext

An unsigned 64-bitfield that represents a unique identifier as used by MPIO to address a particular DSM.


### -field DsmVersion

A field that contains an instance of the DSM_VERSION structure with version information for the DSM.


### -field DsmCounters

A field that contains an instance of the DSM_COUNTERS structure with timer counters information that is specific to the particular DSM.

