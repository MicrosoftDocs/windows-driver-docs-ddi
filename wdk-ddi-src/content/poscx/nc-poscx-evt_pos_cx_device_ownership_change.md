---
UID: NC:poscx.EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE
title: EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE (poscx.h)
description: The EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE callback is called during the API claim ownership transition. The driver is expected to set the device back to a default state in this routine.
old-location: pos\evt_pos_cx_device_ownership_change.htm
tech.root: pos
ms.assetid: 9587928C-6C40-4550-820A-B77968E3E16A
ms.date: 02/23/2018
keywords: ["EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE callback function"]
ms.keywords: EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE, EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE callback, EvtPosCxDeviceOwnershipChange, EvtPosCxDeviceOwnershipChange callback function, pos.evt_pos_cx_device_ownership_change, poscx/EvtPosCxDeviceOwnershipChange
f1_keywords:
 - "poscx/EvtPosCxDeviceOwnershipChange"
 - "EvtPosCxDeviceOwnershipChange"
req.header: poscx.h
req.include-header: Poscx.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- poscx.h
api_name:
- EvtPosCxDeviceOwnershipChange
product:
- Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE callback function


## -description


The 
  EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE callback is called during the API claim ownership transition. The driver is expected to set the device back to a default state in this routine.


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param oldOwnerFileObj [in, optional]

The file object of the previous claim owner. This may be NULL if no previous owner.


### -param newOwnerFileObj [in, optional]

The file object of the new claim owner. This may be NULL if the device was released without a pending claim request.


