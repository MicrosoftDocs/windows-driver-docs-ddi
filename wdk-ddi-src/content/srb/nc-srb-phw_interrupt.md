---
UID: NC:srb.PHW_INTERRUPT
title: PHW_INTERRUPT (srb.h)
description: The PHW_INTERRUPT routine prototype declares the miniport driver's interrupt handler routine.
old-location: storage\phw_interrupt.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["PHW_INTERRUPT callback"]
ms.keywords: "(*PHW_INTERRUPT), (*PHW_INTERRUPT) callback function [Storage Devices], ide_minikr_d0fa2a3d-deef-45c5-9251-a3c30c7af434.xml, srb/(*PHW_INTERRUPT), storage.phw_interrupt"
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
 - PHW_INTERRUPT
 - srb/PHW_INTERRUPT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - srb.h
api_name:
 - (*PHW_INTERRUPT)
---

# PHW_INTERRUPT callback (srb.h)


## -description

The PHW_INTERRUPT routine prototype declares the miniport driver's interrupt handler routine.

## -parameters

### -param DeviceExtension 

[in]
Pointer to the miniport driver's per-HBA storage area.

## -returns

If the interrupt handler routine determines that its HBA generated the interrupt, it returns <b>TRUE</b>. If the interrupt handler determines that its HBA did not generate the interrupt, it should return <b>FALSE</b> as soon as possible.

## -remarks

The interrupt handler routine for both SCSI and StorPort miniport drivers are declared using this prototype.

For more information about the SCSI miniport driver's interrupt handler routine see <a href="/previous-versions/windows/hardware/drivers/ff557312(v=vs.85)">HwScsiInterrupt</a>.

For more information about the miniport driver's interrupt handler routine that is used with the StorPort driver see <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_interrupt">HwStorInterrupt</a>.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff557312(v=vs.85)">HwScsiInterrupt</a>



<a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_interrupt">HwStorInterrupt</a>
