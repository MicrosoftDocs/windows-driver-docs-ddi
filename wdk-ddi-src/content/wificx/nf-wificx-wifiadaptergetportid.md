---
UID: NF:wificx.WifiAdapterGetPortId
tech.root: netvista
<<<<<<< HEAD
title: WifiAdapterGetPortId (wificx.h)
ms.date: 08/30/2021
ms.topic: language-reference
targetos: Windows
description: The WifiAdapterGetPortId function gets the Wi-Fi adapter port ID.
=======
title: WifiAdapterGetPortId
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WifiAdapterGetPortId function for internal use only. Don't use this function in your code."
>>>>>>> main
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11 
=======
req.target-min-winverclnt: Windows 11
>>>>>>> main
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
 - wificx.h
api_name:
 - WifiAdapterGetPortId
f1_keywords:
 - WifiAdapterGetPortId
 - wificx/WifiAdapterGetPortId
dev_langs:
 - c++
---

## -description

The **WifiAdapterGetPortId** function gets the Wi-Fi adapter port ID.

## -parameters

### -param Adapter

[_In_] A handle to a NETADAPTER object that the client driver obtained from a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

## -returns

Returns the the Wi-Fi adapter port ID.

## -remarks

## -see-also

