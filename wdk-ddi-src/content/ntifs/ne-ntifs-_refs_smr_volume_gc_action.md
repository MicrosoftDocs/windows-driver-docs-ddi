---
UID: NE:ntifs._REFS_SMR_VOLUME_GC_ACTION
title: _REFS_SMR_VOLUME_GC_ACTION (ntifs.h)
description: The REFS_SMR_VOLUME_GC_ACTION enum contains the available garbage collection commands for FSCTL_SET_REFS_SMR_VOLUME_GC_PARAMETERS.
old-location: ifsk\refs_smr_volume_gc_action.htm
tech.root: ifsk
ms.assetid: 9A9D174A-0E9E-4B3A-BF91-3000128C58C7
ms.date: 04/16/2018
keywords: ["_REFS_SMR_VOLUME_GC_ACTION enumeration"]
ms.keywords: "*PREFS_SMR_VOLUME_GC_ACTION, PREFS_SMR_VOLUME_GC_ACTION, PREFS_SMR_VOLUME_GC_ACTION enumeration pointer [Installable File System Drivers], REFS_SMR_VOLUME_GC_ACTION, REFS_SMR_VOLUME_GC_ACTION enumeration [Installable File System Drivers], SmrGcActionPause, SmrGcActionStart, SmrGcActionStartFullSpeed, SmrGcActionStop, _REFS_SMR_VOLUME_GC_ACTION, ifsk.refs_smr_volume_gc_action, ntifs/PREFS_SMR_VOLUME_GC_ACTION, ntifs/REFS_SMR_VOLUME_GC_ACTION, ntifs/SmrGcActionPause, ntifs/SmrGcActionStart, ntifs/SmrGcActionStartFullSpeed, ntifs/SmrGcActionStop"
f1_keywords:
 - "ntifs/REFS_SMR_VOLUME_GC_ACTION"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntifs.h
api_name:
- REFS_SMR_VOLUME_GC_ACTION
product:
- Windows
targetos: Windows
req.typenames: REFS_SMR_VOLUME_GC_ACTION, *PREFS_SMR_VOLUME_GC_ACTION
---

# _REFS_SMR_VOLUME_GC_ACTION enumeration


## -description


The <b>REFS_SMR_VOLUME_GC_ACTION</b> enum contains the available garbage collection commands for <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-set-refs-smr-volume-gc-parameters">FSCTL_SET_REFS_SMR_VOLUME_GC_PARAMETERS</a>.


## -enum-fields




### -field SmrGcActionStart

Specifies to start garbage collection or resume from a previously paused garbage collection.  By default, garbage collection is off on Shingled Magnetic Recording (SMR) volumes.  Only users with admin rights can modify this setting.


### -field SmrGcActionStartFullSpeed

Specifies to start or resume garbage collection at full speed.  Issuing Read/ Write I/O up to one SMR band size (256mb) at a time.


### -field SmrGcActionPause

Specifies to temporarily stop the garbage collection if it's in progress.  If the garbage collection is not in progress, there will be no operation.


### -field SmrGcActionStop

Specifies to stop the garbage collection process and removes the ability to resume.  If garbage collection was paused previously, this will clear the ability to resume from the point of the pause.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-set-refs-smr-volume-gc-parameters">FSCTL_SET_REFS_SMR_VOLUME_GC_PARAMETERS</a>
 

 

