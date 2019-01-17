---
UID: NC:srb.PHW_INITIALIZE
title: PHW_INITIALIZE
description: The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs.
old-location: storage\phw_initialize.htm
tech.root: storage
ms.assetid: dd678196-62f6-4c27-845f-a9b52c663e2a
ms.date: 03/29/2018
ms.keywords: "(*PHW_INITIALIZE), (*PHW_INITIALIZE) callback function [Storage Devices], ide_minikr_95bb126d-6d4c-4091-b2fa-6b891d587186.xml, srb/(*PHW_INITIALIZE), storage.phw_initialize"
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	srb.h
api_name:
-	(*PHW_INITIALIZE)
product:
- Windows
targetos: Windows
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# PHW_INITIALIZE callback


## -description


The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs.


## -parameters




### -param DeviceExtension [in]

Pointer to the miniport driver's per-HBA storage area.


## -returns



If the operation succeeds, the initialization routine returns <b>TRUE</b>. Otherwise, the initialize routine returns <b>FALSE</b>.




## -remarks



The initialization routine for both SCSI and StorPort miniport drivers are declared using this prototype.

For more information about the SCSI miniport driver initialization routine see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557302">HwScsiInitialize</a>.

For more information about the miniport driver initialization routine that is used with the StorPort driver see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557396">HwStorInitialize</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557302">HwScsiInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557396">HwStorInitialize</a>
 

 

