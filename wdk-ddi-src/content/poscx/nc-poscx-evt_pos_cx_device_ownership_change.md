---
UID: NC:poscx.EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE
title: EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE
author: windows-driver-content
description: The EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE callback is called during the API claim ownership transition. The driver is expected to set the device back to a default state in this routine.
old-location: pos\evt_pos_cx_device_ownership_change.htm
old-project: pos
ms.assetid: 9587928C-6C40-4550-820A-B77968E3E16A
ms.author: windowsdriverdev
ms.date: 2/19/2018
ms.keywords: pos.evt_pos_cx_device_ownership_change, EvtPosCxDeviceOwnershipChange callback function, EvtPosCxDeviceOwnershipChange, EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE, EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE, poscx/EvtPosCxDeviceOwnershipChange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	poscx.h
apiname:
-	EvtPosCxDeviceOwnershipChange
product: Windows
targetos: Windows
req.typenames: PCFILTER_DESCRIPTOR, *PPCFILTER_DESCRIPTOR
req.product: Windows 10 or later.
---

# EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE callback


## -description


The 
  EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE callback is called during the API claim ownership transition. The driver is expected to set the device back to a default state in this routine.


## -prototype


````
EVT_POS_CX_DEVICE_OWNERSHIP_CHANGE EvtPosCxDeviceOwnershipChange;

VOID EvtPosCxDeviceOwnershipChange(
  _In_     WDFDEVICE     device,
  _In_opt_ WDFFILEOBJECT oldOwnerFileObj,
  _In_opt_ WDFFILEOBJECT newOwnerFileObj
)
{ ... }
````


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param oldOwnerFileObj [in, optional]

The file object of the previous claim owner. This may be NULL if no previous owner.


### -param newOwnerFileObj [in, optional]

The file object of the new claim owner. This may be NULL if the device was released without a pending claim request.


## -returns



This callback function does not return a value.



