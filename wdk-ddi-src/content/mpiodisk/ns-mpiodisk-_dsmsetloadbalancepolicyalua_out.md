---
UID: NS:mpiodisk._DsmSetLoadBalancePolicyALUA_OUT
title: _DsmSetLoadBalancePolicyALUA_OUT
author: windows-driver-content
description: The DsmSetLoadBalancePolicyALUA_OUT structure reports the output of the DsmSetLoadBalancePolicyALUA method.
old-location: storage\dsmsetloadbalancepolicyalua_out.htm
old-project: storage
ms.assetid: 00c5f766-299e-4c07-a3e0-61077518a37a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DsmSetLoadBalancePolicyALUA_OUT, DsmSetLoadBalancePolicyALUA_OUT, *PDsmSetLoadBalancePolicyALUA_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiodisk.h
req.include-header: Mpiowmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DsmSetLoadBalancePolicyALUA_OUT
req.alt-loc: mpiodisk.h
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
req.typenames: DsmSetLoadBalancePolicyALUA_OUT, *PDsmSetLoadBalancePolicyALUA_OUT
---

# _DsmSetLoadBalancePolicyALUA_OUT structure



## -description
The<b> DsmSetLoadBalancePolicyALUA_OUT</b> structure reports the output of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552672">DsmSetLoadBalancePolicyALUA</a> method.



## -syntax

````
typedef struct _DsmSetLoadBalancePolicyALUA_OUT {
  ULONG Status;
} DsmSetLoadBalancePolicyALUA_OUT, *PDsmSetLoadBalancePolicyALUA_OUT;
````


## -struct-fields

### -field Status

The status of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552672">DsmSetLoadBalancePolicyALUA</a> operation.


## -remarks
