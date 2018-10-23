---
UID: NF:fcb.RxGetFileSizeWithLock
title: RxGetFileSizeWithLock function
author: windows-driver-content
description: RxGetFileSizeWithLock gets the file size in the FCB structure using a lock to ensure that the 64-bit value is read consistently.
old-location: ifsk\rxgetfilesizewithlock.htm
tech.root: ifsk
ms.assetid: f58c2a7a-0782-47a7-84e6-98df541c875d
ms.date: 04/16/2018
ms.keywords: RxGetFileSizeWithLock, RxGetFileSizeWithLock function [Installable File System Drivers], fcb/RxGetFileSizeWithLock, ifsk.rxgetfilesizewithlock, rxref_15aee1e0-d82a-45ea-ad0b-e610347c62fe.xml
ms.topic: function
req.header: fcb.h
req.include-header: Mrxfcb.h, Fcb.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fcb.h
api_name:
-	RxGetFileSizeWithLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxGetFileSizeWithLock function


## -description


<b>RxGetFileSizeWithLock</b> gets the file size in the FCB structure using a lock to ensure that the 64-bit value is read consistently.


## -parameters




### -param Fcb [in]

A pointer to the FCB structure.


### -param FileSize [out]

A pointer where the file size file will be stored on output.


## -returns



None




## -remarks



The <b>RxGetFileSizeWithLock</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when an I/O request packet is received for IRP_MJ_QUERY_INFORMATION, IRP_MJ_SET_INFORMATION, IRP_MJ_READ, or IRP_MJ_WRITE. These IRPs are normally received by RDBSS in response to a user-mode application requesting operations on a file. It is also possible for another kernel driver to issue such an IRP. 

These IRPs will normally result in a call to one of the <b>MRxQueryFileInfo, MRxQuerySdInfo</b>, <b>MRxLowIORead</b>, or <b>MRxLowIOWrite</b> routines provided by the network mini-redirector. 

<b>RxGetFileSizeWithLock</b> acquires a lock on the FCB structure and then reads the file size, and then frees the lock. This lock assures that the file size is protected during this operation, since file size is a 64-bit quantity that requires at least two instructions to read on 32-bit processors. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550770">MRxQueryFileInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550776">MRxQuerySdInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-fcb-structure">The FCB Structure</a>
 

 

