---
UID: NS:mpiodisk._DsmSetLoadBalancePolicy_OUT
title: _DsmSetLoadBalancePolicy_OUT
author: windows-driver-content
description: The DsmSetLoadBalancePolicy_OUT structure reports the output parameter of the DsmSetLoadBalancePolicy method.
old-location: storage\dsmsetloadbalancepolicy_out.htm
old-project: storage
ms.assetid: d3479656-310f-4e2d-a671-296bc3e2f1ab
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DsmSetLoadBalancePolicy_OUT, DsmSetLoadBalancePolicy_OUT, *PDsmSetLoadBalancePolicy_OUT
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
req.alt-api: DsmSetLoadBalancePolicy_OUT
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
req.typenames: DsmSetLoadBalancePolicy_OUT, *PDsmSetLoadBalancePolicy_OUT
---

# _DsmSetLoadBalancePolicy_OUT structure



## -description
The <b>DsmSetLoadBalancePolicy_OUT</b> structure reports the output parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552670">DsmSetLoadBalancePolicy</a> method.



## -syntax

````
typedef struct _DsmSetLoadBalancePolicy_OUT {
  ULONG Status;
} DsmSetLoadBalancePolicy_OUT, *PDsmSetLoadBalancePolicy_OUT;
````


## -struct-fields

### -field Status

The status of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552670">DsmSetLoadBalancePolicy</a> operation.


## -remarks
