---
UID: NF:wdm.PoSetSystemWakeDevice
tech.root: kernel
title: PoSetSystemWakeDevice
ms.date: 06/03/2021
targetos: Windows
description: The PoSetSystemWakeDevice function attempts to extract a PDO from the supplied device object.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - PoSetSystemWakeDevice
f1_keywords:
 - PoSetSystemWakeDevice
 - wdm/PoSetSystemWakeDevice
dev_langs:
 - c++
---

## -description

The **PoSetSystemWakeDevice** function attempts to extract a PDO from the supplied device object. If a valid PDO is found then it is added to the list of sources which contributed to waking the system from a sleep state. There is a time interval (currently 2 seconds) during which, from the completed wait/wake IRPs, the power manager attempts to build a list of system wake sources.

## -parameters

### -param DeviceObject

[in]
Supplies a pointer to the device object that has wait/wake IRPs contributing to waking the system from a sleep state.

## -remarks

## -see-also
