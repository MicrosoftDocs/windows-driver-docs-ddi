---
UID: NF:ndis.NdisInterlockedAddLargeStatistic
title: NdisInterlockedAddLargeStatistic macro
author: windows-driver-content
description: The NdisInterlockedAddLargeStatistic function performs an interlocked addition of a ULONG increment value to a LARGE_INTEGER addend value.
old-location: netvista\ndisinterlockedaddlargestatistic.htm
old-project: netvista
ms.assetid: 7bc753b1-5e09-431b-b226-fb7194dd6947
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisInterlockedAddLargeStatistic, NdisInterlockedAddLargeStatistic macro [Network Drivers Starting with Windows Vista], ndis/NdisInterlockedAddLargeStatistic, ndis_interlocked_ref_f1b7622e-acc8-45d7-b85e-c39058b595fe.xml, netvista.ndisinterlockedaddlargestatistic
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisInterlockedAddLargeStatistic (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisInterlockedAddLargeStatistic (NDIS 5.1)) in Windows XP.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisInterlockedAddLargeStatistic
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisInterlockedAddLargeStatistic macro


## -description


The 
  <b>NdisInterlockedAddLargeStatistic</b> function performs an interlocked addition of a ULONG increment value
  to a LARGE_INTEGER addend value.


## -parameters




### -param _Addend [in]

A pointer to a LARGE_INTEGER value that is incremented by the value of 
     <i>Increment</i> .


### -param _Increment [in]

A ULONG value that is added to the value to which the 
     <i>Addend</i> parameter points.


## -remarks



Functions that perform interlocked operations must not cause a page fault to occur. Neither their code
    nor any of the data that they access can cause a page fault without bringing down the local computer.

<b>NdisInterlockedAddLargeStatistic</b> masks interrupts and can be safely used to synchronize a driver's 
    <a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a> function with other
    driver code.




## -see-also




<a href="https://msdn.microsoft.com/810503b9-75cd-4b38-ab1f-de240968ded6">MiniportInterrupt</a>
 

 

