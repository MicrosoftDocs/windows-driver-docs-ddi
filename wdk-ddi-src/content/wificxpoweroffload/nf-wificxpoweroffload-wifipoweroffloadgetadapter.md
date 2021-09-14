---
UID: NF:wificxpoweroffload.WifiPowerOffloadGetAdapter
tech.root: netvista
title: WifiPowerOffloadGetAdapter (wificxpoweroffload.h)
ms.date: 09/10/2021
targetos: Windows
description: The WifiPowerOffloadGetAdapter function gets the Wi-Fi adapter for alow power protocol offload.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificxpoweroffload.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificxpoweroffload.h
api_name:
 - WifiPowerOffloadGetAdapter
f1_keywords:
 - WifiPowerOffloadGetAdapter
 - wificxpoweroffload/WifiPowerOffloadGetAdapter
dev_langs:
 - c++
---

## -description

The **WifiPowerOffloadGetAdapter** function gets the Wi-Fi adapter for a low power protocol offload.

## -parameters

### -param WifiPowerOffload

[_In_] The WIFIPOWEROFFLOAD object that represents this power offload.

## -returns

Returns the NETADAPTER object that represents the Wi-Fi adapter for this power offload.

## -remarks

## -see-also

[**WifiPowerOffloadGetType**](nf-wificxpoweroffload-wifipoweroffloadgettype.md)

