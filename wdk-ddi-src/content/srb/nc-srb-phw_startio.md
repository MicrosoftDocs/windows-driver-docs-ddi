---
UID: NC:srb.PHW_STARTIO
title: PHW_STARTIO (srb.h)
description: The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs.
old-location: storage\phw_startio.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["PHW_STARTIO callback"]
ms.keywords: "(*PHW_STARTIO), (*PHW_STARTIO) callback function [Storage Devices], ide_minikr_16fd699a-4cb9-4741-9e50-3fa8177f49f2.xml, srb/(*PHW_STARTIO), storage.phw_startio"
req.header: srb.h
req.include-header: Storport.h, Srb.h, Storport.h
req.target-type: Desktop
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
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
f1_keywords:
 - PHW_STARTIO
 - srb/PHW_STARTIO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - srb.h
api_name:
 - PHW_STARTIO
---

# PHW_STARTIO callback


## -description

The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs.

## -parameters

### -param DeviceExtension 

[in]
Pointer to the miniport driver's per-HBA storage area.

### -param Srb 

[in]
Pointer to the SCSI request block to be started.

## -returns

The start I/O routine returns <b>TRUE</b> to acknowledge receipt of the SCSI request block (SRB). If the start I/O routine does not receive a well-formed SRB, it returns <b>FALSE</b>.

## -remarks

The start routine for both SCSI and StorPort miniport drivers are declared using this prototype.

For more information about the SCSI miniport driver's start I/O routine see <a href="/previous-versions/windows/hardware/drivers/ff557323(v=vs.85)">HwScsiStartIo</a>.

For more information about the miniport driver's start I/O routine that is used with the StorPort driver see <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_startio">HwStorStartIo</a>.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff557323(v=vs.85)">HwScsiStartIo</a>



<a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_startio">HwStorStartIo</a>

