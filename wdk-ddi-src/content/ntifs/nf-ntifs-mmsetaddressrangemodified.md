---
UID: NF:ntifs.MmSetAddressRangeModified
title: MmSetAddressRangeModified function
author: windows-driver-content
description: The MmSetAddressRangeModified routine marks currently valid pages in the specified range of the system cache as modified.
old-location: ifsk\mmsetaddressrangemodified.htm
old-project: ifsk
ms.assetid: c903485f-205e-4679-99a7-2a644731fa77
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntifs/MmSetAddressRangeModified, MmSetAddressRangeModified routine [Installable File System Drivers], MmSetAddressRangeModified, mmref_4d6ef497-4a72-4fed-8422-365708740cc7.xml, ifsk.mmsetaddressrangemodified
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmSetAddressRangeModified
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# MmSetAddressRangeModified function


## -description


The <b>MmSetAddressRangeModified</b> routine marks currently valid pages in the specified range of the system cache as modified.


## -syntax


````
BOOLEAN MmSetAddressRangeModified(
  _In_ PVOID  Address,
  _In_ SIZE_T Length
);
````


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

<a href="..\ntifs\nf-ntifs-ccistheredirtydata.md">CcIsThereDirtyData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20MmSetAddressRangeModified routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

