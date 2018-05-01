---
UID: NF:ntifs.MmSetAddressRangeModified
title: MmSetAddressRangeModified function
author: windows-driver-content
description: The MmSetAddressRangeModified routine marks currently valid pages in the specified range of the system cache as modified.
old-location: ifsk\mmsetaddressrangemodified.htm
old-project: ifsk
ms.assetid: c903485f-205e-4679-99a7-2a644731fa77
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: MmSetAddressRangeModified, MmSetAddressRangeModified routine [Installable File System Drivers], ifsk.mmsetaddressrangemodified, mmref_4d6ef497-4a72-4fed-8422-365708740cc7.xml, ntifs/MmSetAddressRangeModified
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmSetAddressRangeModified
product: Windows
targetos: Windows
req.typenames: 
---

# MmSetAddressRangeModified function


## -description


The <b>MmSetAddressRangeModified</b> routine marks currently valid pages in the specified range of the system cache as modified.


## -parameters




### -param Address [in]

Address of the start of the range.


### -param Length [in]

Length of the range in bytes.


## -returns



<b>MmSetAddressRangeModified</b> returns <b>TRUE</b> if it marked at least one page in the range as modified, <b>FALSE</b> otherwise.




## -remarks



The entire range specified by <i>Address</i> and <i>Length</i> must reside within the system cache.

For more information about memory management, see <a href="https://msdn.microsoft.com/e030a37c-26ab-4177-9980-4336928975e1">Memory Management</a>. 

Callers of <b>MmSetAddressRangeModified</b> must be running at IRQL &lt; DISPATCH_LEVEL for pageable addresses, and IRQL &lt;= DISPATCH_LEVEL for nonpageable addresses.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539145">CcIsThereDirtyData</a>
 

 

