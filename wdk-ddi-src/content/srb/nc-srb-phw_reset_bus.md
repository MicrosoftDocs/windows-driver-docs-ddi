---
UID: NC:srb.PHW_RESET_BUS
title: PHW_RESET_BUS (srb.h)
description: The PHW_RESET_BUS prototype declares a routine that resets the indicated SCSI bus.
old-location: storage\phw_reset_bus.htm
tech.root: storage
ms.assetid: 8c41ca6d-4b55-4858-b8bb-d7b2e682a8f7
ms.date: 03/29/2018
keywords: ["PHW_RESET_BUS callback"]
ms.keywords: "(*PHW_RESET_BUS), (*PHW_RESET_BUS) callback function [Storage Devices], ide_minikr_6cda3e23-0fa6-48dd-a0c0-3d47287eb829.xml, srb/(*PHW_RESET_BUS), storage.phw_reset_bus"
f1_keywords:
 - "srb/(*PHW_RESET_BUS)"
 - "(*PHW_RESET_BUS)"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- srb.h
api_name:
- (*PHW_RESET_BUS)
targetos: Windows
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# PHW_RESET_BUS callback


## -description


The PHW_RESET_BUS prototype declares a routine that resets the indicated SCSI bus.


## -parameters




### -param DeviceExtension [in]

Pointer to the miniport driver's per-HBA storage area.


### -param PathId [in]

Contains a number that identifies the SCSI bus to be reset.


## -returns



The routine that this prototype declares returns <b>TRUE</b> if the bus is successfully reset. The routine returns <b>FALSE</b> if the bus is not successfully reset.




## -remarks



The initialization routine for both SCSI and StorPort miniport drivers are declared using this prototype.

For more information about the SCSI miniport driver's bus reset routine see <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557318(v=vs.85)">HwScsiResetBus</a>.

For more information about the bus reset routine that is used with the StorPort driver's miniport driver routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_reset_bus">HwStorResetBus</a>.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557318(v=vs.85)">HwScsiResetBus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_reset_bus">HwStorResetBus</a>
 

 

