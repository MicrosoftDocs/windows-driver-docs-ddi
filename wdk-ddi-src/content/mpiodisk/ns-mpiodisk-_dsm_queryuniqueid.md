---
UID: NS:mpiodisk._DSM_QueryUniqueId
title: _DSM_QueryUniqueId
author: windows-driver-content
description: The DSM_QueryUniqueId structure is used to query the DSM for a unique identifier.
old-location: storage\dsm_queryuniqueid.htm
old-project: storage
ms.assetid: 023390a1-e878-4f1f-a5c2-1545a6786aaa
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: mpiodisk/DSM_QueryUniqueId, mpiodisk/PDSM_QueryUniqueId, _DSM_QueryUniqueId, *PDSM_QueryUniqueId, PDSM_QueryUniqueId structure pointer [Storage Devices], structs-scsibus_eb6e8cc6-4b6a-468f-a14c-7a11c827ef30.xml, storage.dsm_queryuniqueid, PDSM_QueryUniqueId, DSM_QueryUniqueId, DSM_QueryUniqueId structure [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiodisk.h
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	mpiodisk.h
apiname: 
-	DSM_QueryUniqueId
product: Windows
targetos: Windows
req.typenames: *PDSM_QueryUniqueId, DSM_QueryUniqueId
---

# _DSM_QueryUniqueId structure


## -description


The DSM_QueryUniqueId structure is used to query the DSM for a unique identifier. This unique identifier can be used together with the DsmPathId to create a 128-bit identifier for a path that is unique among all paths, as well as all DSMs, that are known to a management application. This is especially useful if the management application is managing devices that are spread across various systems. To query for this 64-bit unique identifier, the application must target the request to a pseudo-LUN that is addressed by its WMI instance name. This class is mandatory for any DSM that supports VDS.


## -syntax


````
typedef struct _DSM_QueryUniqueId {
  ULONGLONG DsmUniqueId;
} DSM_QueryUniqueId, *PDSM_QueryUniqueId;
````


## -struct-fields




### -field DsmUniqueId

An unsigned 64-bitfield that represents an identifier that must be set by DSMs that want management applications, such as VDS, to be able to manage the devices that are controlled by the particular DSM. This structure is used together with the DsmPathId structure to create a 128-bit identifier that is unique, not just among all the paths that are known to this DSM, but also among all the DSMs that are present in the system.

