---
UID: NF:ndis.NdisInterlockedAddUlong
title: NdisInterlockedAddUlong macro
author: windows-driver-content
description: The NdisInterlockedAddUlong function adds an unsigned long value to a given unsigned integer as an atomic operation, using a caller-supplied spin lock to synchronize access to the integer variable.
old-location: netvista\ndisinterlockedaddulong.htm
old-project: netvista
ms.assetid: d2e31f3c-7152-4df9-8206-a15dee9b641f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: NdisInterlockedAddUlong, NdisInterlockedAddUlong macro [Network Drivers Starting with Windows Vista], ndis/NdisInterlockedAddUlong, ndis_interlocked_ref_0b4862c9-6897-4b73-ab23-5cd2ede3e82a.xml, netvista.ndisinterlockedaddulong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisInterlockedAddUlong
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisInterlockedAddUlong macro


## -description


The 
  <b>NdisInterlockedAddUlong</b> function adds an unsigned long value to a given unsigned integer as an atomic
  operation, using a caller-supplied spin lock to synchronize access to the integer variable.


## -syntax


````
VOID NdisInterlockedAddUlong(
  [in] PULONG          Addend,
  [in] ULONG           Increment,
  [in] PNDIS_SPIN_LOCK SpinLock
);
````


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
    <a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a> function before
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

<a href="..\ndis\nf-ndis-ndisstoreulong.md">NdisStoreUlong</a>



<a href="..\ndis\nf-ndis-ndisreleasespinlock.md">NdisReleaseSpinLock</a>



<a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a>



<a href="..\ndis\nf-ndis-ndisretrieveulong.md">NdisRetrieveUlong</a>



<a href="..\ndis\nf-ndis-ndisacquirespinlock.md">NdisAcquireSpinLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInterlockedAddUlong macro%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

