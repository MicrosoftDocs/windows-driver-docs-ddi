---
UID: NC:srb.PHW_STARTIO
title: PHW_STARTIO
author: windows-driver-content
description: The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs.
old-location: storage\phw_startio.htm
tech.root: storage
ms.assetid: 1b177ef5-2b58-425e-9b9a-428bbe15de69
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "(*PHW_STARTIO), (*PHW_STARTIO) callback function [Storage Devices], ide_minikr_16fd699a-4cb9-4741-9e50-3fa8177f49f2.xml, srb/(*PHW_STARTIO), storage.phw_startio"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	(*PHW_STARTIO)
product:
- Windows
targetos: Windows
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# PHW_STARTIO callback


## -description


The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs.


## -parameters




### -param DeviceExtension [in]

Pointer to the miniport driver's per-HBA storage area.


### -param Srb [in]

Pointer to the SCSI request block to be started.


## -returns



The start I/O routine returns <b>TRUE</b> to acknowledge receipt of the SCSI request block (SRB). If the start I/O routine does not receive a well-formed SRB, it returns <b>FALSE</b>.




## -remarks



The start routine for both SCSI and StorPort miniport drivers are declared using this prototype.

For more information about the SCSI miniport driver's start I/O routine see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557323">HwScsiStartIo</a>.

For more information about the miniport driver's start I/O routine that is used with the StorPort driver see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557423">HwStorStartIo</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557323">HwScsiStartIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557423">HwStorStartIo</a>
 

 

