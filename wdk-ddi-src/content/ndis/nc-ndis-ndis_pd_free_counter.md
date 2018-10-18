---
UID: NC:ndis.NDIS_PD_FREE_COUNTER
title: NDIS_PD_FREE_COUNTER
author: windows-driver-content
description: The PacketDirect (PD) platform calls a PD-capable miniport driver's NdisPDFreeCounter function to free a counter object.
old-location: netvista\ndispdfreecounter.htm
tech.root: netvista
ms.assetid: 60C47437-A999-4F82-B144-6F77410E5C07
ms.date: 5/2/2018
ms.keywords: NDIS_PD_FREE_COUNTER, NDIS_PD_FREE_COUNTER callback, NdisPDFreeCounter, NdisPDFreeCounter callback function [Network Drivers Starting with Windows Vista], ndis/NdisPDFreeCounter, netvista.ndispdfreecounter
ms.topic: callback
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	NdisPDFreeCounter
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_PD_FREE_COUNTER callback function


## -description


The PacketDirect (PD) platform calls a PD-capable miniport driver's 
   <i>NdisPDFreeCounter</i> function to free a counter object.<div class="alert"><b>Note</b>  You must declare the function by using the <b>NDIS_PD_FREE_COUNTER</b> type. For more
   information, see the following Examples section.</div>
<div> </div>



## -parameters




### -param CounterHandle [in]

A counter handle that the miniport driver allocated in its <a href="https://msdn.microsoft.com/86AA537D-952F-4A7A-ACA4-24B8C1AE932A">NdisPDAllocateCounter</a> function.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/86AA537D-952F-4A7A-ACA4-24B8C1AE932A">NdisPDAllocateCounter</a>
 

 

