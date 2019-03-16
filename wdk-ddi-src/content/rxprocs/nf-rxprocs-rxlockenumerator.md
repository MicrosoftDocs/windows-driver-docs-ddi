---
UID: NF:rxprocs.RxLockEnumerator
title: RxLockEnumerator function (rxprocs.h)
description: RxLockEnumerator is called from a network mini-redirector to enumerate the file locks on an FCB.
old-location: ifsk\rxlockenumerator.htm
tech.root: ifsk
ms.assetid: 8d14604f-c9e5-4a2d-bb51-ef1925b39118
ms.date: 04/16/2018
ms.keywords: RxLockEnumerator, RxLockEnumerator function [Installable File System Drivers], ifsk.rxlockenumerator, rxprocs/RxLockEnumerator, rxref_62372da9-aa80-447e-8e79-6bc1f1c5cf54.xml
ms.topic: function
req.header: rxprocs.h
req.include-header: Rxprocs.h, Mrxfcb.h, Fcb.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rxprocs.h
api_name:
- RxLockEnumerator
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxLockEnumerator function


## -description


<b>RxLockEnumerator</b> is called from a network mini-redirector to enumerate the file locks on an FCB.


## -parameters




### -param SrvOpen [in, out]

A pointer to the SRV_OPEN structure on the FCB to be enumerated.


### -param ContinuationHandle [in, out]

A pointer to a handle passed back and forth representing the state of the enumeration. If this parameter is a <b>NULL</b> pointer, then this is the start of an lock enumeration.


### -param FileOffset [out]

A pointer to the file offset of the returned lock.


### -param LockRange [out]

A pointer to the lock range of the returned lock.


### -param IsLockExclusive [out]

A pointer to a BOOLEAN indicating if the returned lock is an exclusive lock.


## -returns



<b>RxLockEnumerator </b>returns <b>TRUE</b> on success indicating that the returned lock data is valid. The <b>RxLockEnumerator </b>routine returns or <b>FALSE</b> on failure when no lock data is found or the end of the list of locks has been reached. 




## -remarks



<b>RxLockEnumerator</b> is normally called from a network min-redirector to enumerate the file locks on an FCB. <b>RxLockEnumerator</b> gets one lock on each call. so the caller needs to keep the enumeration state internally. As a result, only one enumeration process can be in progress at any time. 

The <b>RxLockEnumerator</b> routine needs to allocate non-paged pool memory in order to enumerate locks. Consequently, <b>RxLockEnumerator</b> can fail if the memory allocation fails. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-fcb-structure">The FCB Structure</a>



<a href="https://msdn.microsoft.com/6cf4c6f6-a21f-4919-92b5-2403b650d8d0">The SRV_OPEN Structure</a>
 

 

