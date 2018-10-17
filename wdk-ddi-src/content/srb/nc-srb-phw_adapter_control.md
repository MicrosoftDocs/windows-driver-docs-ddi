---
UID: NC:srb.PHW_ADAPTER_CONTROL
title: PHW_ADAPTER_CONTROL
author: windows-driver-content
description: The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs.
old-location: storage\phw_adapter_control.htm
tech.root: storage
ms.assetid: ef58c005-e5e5-409d-9010-59635fd4da02
ms.date: 3/29/2018
ms.keywords: "(*PHW_ADAPTER_CONTROL), (*PHW_ADAPTER_CONTROL) callback function [Storage Devices], ide_minikr_fb5a2e9f-b755-417e-b152-ef680c85c16a.xml, srb/(*PHW_ADAPTER_CONTROL), storage.phw_adapter_control"
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
-	(*PHW_ADAPTER_CONTROL)
product:
- Windows
targetos: Windows
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# PHW_ADAPTER_CONTROL callback


## -description


The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs.


## -parameters




### -param DeviceExtension [in]

Pointer to the miniport driver's per-HBA storage area.


### -param ControlType [in]

Specifies an adapter-control operation. For a list of the allowed operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557274">HwScsiAdapterControl</a>.


### -param Parameters [in]

Contains information related to the <i>ControlType</i>. For an explanation of the meaning of these values, see the discussion accompanying the <i>Parameters</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557274">HwScsiAdapterControl</a>.


## -returns



The routine declared by this prototype returns different sets of values depending on the control type. For a complete description of the return values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557274">HwScsiAdapterControl</a>.




## -remarks



The adapter control routine for both SCSI and StorPort miniport drivers are declared using this prototype.

For more information about the SCSI miniport driver's adapter control routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557274">HwScsiAdapterControl</a>.

For more information about the adapter control routine that is used with the StorPort driver's miniport driver, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557365">HwStorAdapterControl</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557274">HwScsiAdapterControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557365">HwStorAdapterControl</a>
 

 

