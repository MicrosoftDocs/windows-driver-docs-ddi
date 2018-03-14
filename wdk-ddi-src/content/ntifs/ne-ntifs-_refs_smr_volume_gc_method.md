---
UID: NE:ntifs._REFS_SMR_VOLUME_GC_METHOD
title: "_REFS_SMR_VOLUME_GC_METHOD"
author: windows-driver-content
description: The REFS_SMR_VOLUME_GC_METHOD enum specifies the garbage collection method or strategy for FSCTL_SET_REFS_SMR_VOLUME_GC_PARAMETERS.
old-location: ifsk\refs_smr_volume_gc_method.htm
old-project: ifsk
ms.assetid: 6C58EFD4-B5F9-4E2B-AF76-E9614218E0DC
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PREFS_SMR_VOLUME_GC_METHOD, PREFS_SMR_VOLUME_GC_METHOD, PREFS_SMR_VOLUME_GC_METHOD enumeration pointer [Installable File System Drivers], REFS_SMR_VOLUME_GC_METHOD, REFS_SMR_VOLUME_GC_METHOD enumeration [Installable File System Drivers], SmrGcMethodCompaction, SmrGcMethodCompression, SmrGcMethodRotation, _REFS_SMR_VOLUME_GC_METHOD, ifsk.refs_smr_volume_gc_method, ntifs/PREFS_SMR_VOLUME_GC_METHOD, ntifs/REFS_SMR_VOLUME_GC_METHOD, ntifs/SmrGcMethodCompaction, ntifs/SmrGcMethodCompression, ntifs/SmrGcMethodRotation"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntifs.h
api_name:
-	REFS_SMR_VOLUME_GC_METHOD
product: Windows
targetos: Windows
req.typenames: REFS_SMR_VOLUME_GC_METHOD, *PREFS_SMR_VOLUME_GC_METHOD
---

# _REFS_SMR_VOLUME_GC_METHOD enumeration


## -description


The <b>REFS_SMR_VOLUME_GC_METHOD</b> enum specifies the garbage collection method or strategy for <a href="https://msdn.microsoft.com/782542C4-CFC5-4BF7-AF38-3247A3AC6AB9">FSCTL_SET_REFS_SMR_VOLUME_GC_PARAMETERS</a>.


## -syntax


````
typedef enum _REFS_SMR_VOLUME_GC_METHOD { 
  SmrGcMethodCompaction   = 1,
  SmrGcMethodCompression  = 2,
  SmrGcMethodRotation     = 3
} REFS_SMR_VOLUME_GC_METHOD, *PREFS_SMR_VOLUME_GC_METHOD;
````


## -enum-fields




### -field SmrGcMethodCompaction

Specifies the use of the compaction method for garbage collection.  


### -field SmrGcMethodCompression

Specifies the use of the compression method for garbage collection.


### -field SmrGcMethodRotation

Specifies the use of the rotation method for garbage collection. Moves data from one tier to another.


## -remarks



Currently the only supported value  is <b>SmrGcMethodCompaction</b>.




## -see-also

<a href="https://msdn.microsoft.com/782542C4-CFC5-4BF7-AF38-3247A3AC6AB9">FSCTL_SET_REFS_SMR_VOLUME_GC_PARAMETERS</a>



 

 


