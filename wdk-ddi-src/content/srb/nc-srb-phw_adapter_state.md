---
UID: NC:srb.PHW_ADAPTER_STATE
title: PHW_ADAPTER_STATE (srb.h)
description: The PHW_INITIALIZE routine prototype declares a routine that saves or restores the state of the miniport driver's HBA.
old-location: storage\phw_adapter_state.htm
tech.root: storage
ms.assetid: 68483404-5ea7-47f6-a6ae-6909e5b6759e
ms.date: 03/29/2018
keywords: ["PHW_ADAPTER_STATE callback"]
ms.keywords: "(*PHW_ADAPTER_STATE), (*PHW_ADAPTER_STATE) callback function [Storage Devices], ide_minikr_65caac84-2b5a-4977-81ff-d9efc1808dbb.xml, srb/(*PHW_ADAPTER_STATE), storage.phw_adapter_state"
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
 - PHW_ADAPTER_STATE
 - srb/PHW_ADAPTER_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - srb.h
api_name:
 - (*PHW_ADAPTER_STATE)
---

# PHW_ADAPTER_STATE callback


## -description

The PHW_INITIALIZE routine prototype declares a routine that saves or restores the state of the miniport driver's HBA.

## -parameters

### -param DeviceExtension 

[in]
Pointer to the miniport driver's per-HBA storage area.

### -param Context 

[in]
Reserved for system use.

### -param SaveState 

[in]
Indicates, when <b>TRUE</b>, that the miniport driver should save the current state of the HBA until the <a href="/previous-versions/windows/hardware/drivers/ff557278(v=vs.85)">HwScsiAdapterState</a> routine is called again with <i>SaveState</i> set to <b>FALSE</b> to restore the saved state.

## -returns

The routine declared by this prototype returns <b>TRUE</b> if it successfully saved or restored the HBA state, <b>FALSE</b> otherwise.

## -remarks

Only SCSI miniport drivers use this prototype. Miniport drivers that work with the StorPort driver do not use the routine that is declared by this prototype.

For more information about the routine declared by this prototype, see <a href="/previous-versions/windows/hardware/drivers/ff557278(v=vs.85)">HwScsiAdapterState</a>.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff557278(v=vs.85)">HwScsiAdapterState</a>