---
UID: NF:rxprocs.RxLockEnumerator
title: RxLockEnumerator function
author: windows-driver-content
description: RxLockEnumerator is called from a network mini-redirector to enumerate the file locks on an FCB.
old-location: ifsk\rxlockenumerator.htm
old-project: ifsk
ms.assetid: 8d14604f-c9e5-4a2d-bb51-ef1925b39118
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxLockEnumerator, rxref_62372da9-aa80-447e-8e79-6bc1f1c5cf54.xml, ifsk.rxlockenumerator, RxLockEnumerator function [Installable File System Drivers], rxprocs/RxLockEnumerator
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rxprocs.h
apiname:
-	RxLockEnumerator
product: Windows
targetos: Windows
req.typenames: "*PRX_CONTEXT, RX_CONTEXT"
req.product: Windows 10 or later.
---

# RxLockEnumerator function


## -description


<b>RxLockEnumerator</b> is called from a network mini-redirector to enumerate the file locks on an FCB.


## -syntax


````
BOOLEAN RxLockEnumerator(
  _Inout_ PMRX_SRV_OPEN  SrvOpen,
  _Inout_ PVOID          *ContinuationHandle,
  _Out_   PLARGE_INTEGER FileOffset,
  _Out_   PLARGE_INTEGER LockRange,
  _Out_   PBOOLEAN       IsLockExclusive
);
````


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

<a href="https://msdn.microsoft.com/6cf4c6f6-a21f-4919-92b5-2403b650d8d0">The SRV_OPEN Structure</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-fcb-structure">The FCB Structure</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxLockEnumerator function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

