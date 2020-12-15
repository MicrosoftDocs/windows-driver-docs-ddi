---
UID: NF:mbbcx.MBB_DEVICE_WAKE_CAPABILITIES_INIT
title: MBB_DEVICE_WAKE_CAPABILITIES_INIT function (mbbcx.h)
description: The MBB_DEVICE_WAKE_CAPABILITIES_INIT method initializes a MBB_DEVICE_WAKE_CAPABILITIES structure.
tech.root: netvista
ms.date: 11/07/2019
keywords: ["MBB_DEVICE_WAKE_CAPABILITIES_INIT function"]
ms.keywords: MBB_DEVICE_WAKE_CAPABILITIES_INIT
req.header: mbbcx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: Any level as long as target memory is resident
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: Vb
f1_keywords:
 - MBB_DEVICE_WAKE_CAPABILITIES_INIT
 - mbbcx/MBB_DEVICE_WAKE_CAPABILITIES_INIT
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - mbbcx.h
api_name:
 - MBB_DEVICE_WAKE_CAPABILITIES_INIT
product:
 - Windows
---

# MBB_DEVICE_WAKE_CAPABILITIES_INIT function


## -description

The **MBB_DEVICE_WAKE_CAPABILITIES_INIT** method initializes a [**MBB_DEVICE_WAKE_CAPABILITIES**](../mbbcx/ns-mbbcx-_mbb_device_wake_capabilities.md) structure.

## -parameters

### -param Capabilities

A pointer to a driver-allocated [**MBB_DEVICE_WAKE_CAPABILITIES**](../mbbcx/ns-mbbcx-_mbb_device_wake_capabilities.md) structure.

## -returns

This method does not return a value.

## -remarks

This methods zeroes out the memory of the  **MBB_DEVICE_WAKE_CAPABILITIES** structure, then fills in the **Size** member. After calling this method, set the remaining members of the  **MBB_DEVICE_WAKE_CAPABILITIES** structure according to your device's capabilities, then call [**MbbDeviceSetWakeCapabilities**](../mbbcx/nf-mbbcx-mbbdevicesetwakecapabilities.md).

## -see-also

