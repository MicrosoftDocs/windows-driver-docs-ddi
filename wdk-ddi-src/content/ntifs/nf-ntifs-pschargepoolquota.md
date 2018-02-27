---
UID: NF:ntifs.PsChargePoolQuota
title: PsChargePoolQuota function
author: windows-driver-content
description: The PsChargePoolQuota routine charges pool quota of the specified pool type to the specified process.
old-location: ifsk\pschargepoolquota.htm
old-project: ifsk
ms.assetid: c405771c-726f-4003-b3c6-f063dd74187e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PsChargePoolQuota, PsChargePoolQuota routine [Installable File System Drivers], ifsk.pschargepoolquota, ntifs/PsChargePoolQuota, psref_690f1550-4753-4f39-bcf2-bdcf7b80112d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "< DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	PsChargePoolQuota
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# PsChargePoolQuota function


## -description


The <b>PsChargePoolQuota</b> routine charges pool quota of the specified pool type to the specified process. 


## -syntax


````
VOID PsChargePoolQuota(
  _In_ PEPROCESS Process,
  _In_ POOL_TYPE PoolType,
  _In_ ULONG_PTR Amount
);
````


## -parameters




### -param Process [in]

Pointer to the process whose quota is to be charged.


### -param PoolType [in]

Type of pool quota to charge, which can be one of the following: 

<ul>
<li><b>NonPagedPool</b></li>
<li><b>PagedPool</b></li>
<li><b>NonPagedPoolCacheAligned</b></li>
<li><b>PagedPoolCacheAligned</b></li>
</ul>


<b>Note</b>: The <b>NonPagedPoolMustSucceed</b> and <b>NonPagedPoolCacheAlignedMustS</b> pool types are obsolete and should no longer be used. 


### -param Amount [in]

Number of bytes to charge against the pool quota for this process. 


## -returns



None




## -remarks



If insufficient quota exists for the process, quota is not charged, and <b>PsChargePoolQuota</b> raises an exception with the status value STATUS_QUOTA_EXCEEDED. Callers are responsible for handling this exception. Thus calls to <b>PsChargePoolQuota</b> must be wrapped within a driver-supplied exception handler.

Every successful call to <b>PsChargePoolQuota</b> must be matched by a subsequent call to <b>PsReturnPoolQuota</b>.

For more information about memory management, see <a href="https://msdn.microsoft.com/e030a37c-26ab-4177-9980-4336928975e1">Memory Management</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-psreturnpoolquota.md">PsReturnPoolQuota</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PsChargePoolQuota routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

