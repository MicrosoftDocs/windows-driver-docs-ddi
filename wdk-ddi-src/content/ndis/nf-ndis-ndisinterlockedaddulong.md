---
UID: NF:ndis.NdisInterlockedAddUlong
title: NdisInterlockedAddUlong macro (ndis.h)
description: The NdisInterlockedAddUlong function adds an unsigned long value to a given unsigned integer as an atomic operation, using a caller-supplied spin lock to synchronize access to the integer variable.
old-location: netvista\ndisinterlockedaddulong.htm
tech.root: netvista
ms.assetid: d2e31f3c-7152-4df9-8206-a15dee9b641f
ms.date: 05/02/2018
keywords: ["NdisInterlockedAddUlong macro"]
ms.keywords: NdisInterlockedAddUlong, NdisInterlockedAddUlong macro [Network Drivers Starting with Windows Vista], ndis/NdisInterlockedAddUlong, ndis_interlocked_ref_0b4862c9-6897-4b73-ab23-5cd2ede3e82a.xml, netvista.ndisinterlockedaddulong
f1_keywords:
 - "ndis/NdisInterlockedAddUlong"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisInterlockedAddUlong (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisInterlockedAddUlong (NDIS   5.1)) in Windows XP.
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
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisInterlockedAddUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisInterlockedAddUlong macro


## -description


The 
  <b>NdisInterlockedAddUlong</b> function adds an unsigned long value to a given unsigned integer as an atomic
  operation, using a caller-supplied spin lock to synchronize access to the integer variable.


## -parameters




### -param _Addend [in]

A pointer to the variable for which the value is to be adjusted by the given 
     <i>Increment</i> .


### -param _Increment [in]

The value to be added to that at 
     <i>Addend</i> .


### -param _SpinLock [in]

A pointer to a caller-initialized spin lock.


## -remarks



The caller of 
    <b>NdisInterlockedAddUlong</b> must provide resident storage for the spin lock, which must be initialized
    with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a> function before
    the initial call to 
    <b>NdisInterlockedAddUlong</b>.

The 
    <i>SpinLock</i> value that is passed to the 
    <b>NdisInterlockedAddUlong</b> function
    is used to assure that the addition to the variable at the 
    <i>Addend</i> parameter is atomic with respect to any other operations on the same variable that
    synchronize with the same spin lock.

<b>NdisInterlockedAddUlong</b> raises the IRQL to DISPATCH_LEVEL when it acquires the given spin lock and
    restores the original IRQL before it returns control. Consequently, any driver function that calls 
    <b>NdisInterlockedAddUlong</b> cannot be pageable code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisacquirespinlock">NdisAcquireSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreleasespinlock">NdisReleaseSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisretrieveulong">NdisRetrieveUlong</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisstoreulong">NdisStoreUlong</a>
 

 

