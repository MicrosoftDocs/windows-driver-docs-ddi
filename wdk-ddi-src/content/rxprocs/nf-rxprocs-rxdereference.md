---
UID: NF:rxprocs.RxDereference
title: RxDereference function
author: windows-driver-content
description: RxDereference decrements the NodeReferenceCount member of a structure by one for several reference counted data structures used by RDBSS.
old-location: ifsk\rxdereference.htm
old-project: ifsk
ms.assetid: 4f63fc92-56e3-4414-a912-09ed0de59c92
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: rxref_90cd9c96-1fcf-4214-b14f-5065c1e52260.xml, RxDereference function [Installable File System Drivers], rxprocs/RxDereference, ifsk.rxdereference, RxDereference
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxprocs.h
req.include-header: Rxprocs.h
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
-	RxDereference
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxDereference function


## -description


<b>RxDereference</b> decrements the <b>NodeReferenceCount</b> member of a structure by one for several reference counted data structures used by RDBSS. 


## -syntax


````
VOID RxDereference(
  _Inout_ PVOID              Instance,
  _In_    LOCK_HOLDING_STATE LockHoldingState
);
````


## -parameters




### -param Instance [in, out]

A pointer to the reference-counted data structure to be dereferenced. 


### -param LockHoldingState [in]

The mode in which the appropriate lock for this data structure is held. This parameter can be one of the following values for the LOCK_HOLDING_STATE enumeration:





#### LHS_LockNotHeld

A lock is not currently held.



#### LHS_SharedLockHeld

A shared lock is being held.



#### LHS_ExclusiveLockHeld

An exclusive lock is being held.


## -returns



None 




## -remarks



<b>RxDereference</b> can be used to dereference (decrement by one) the <b>NodeReferenceCount</b> member on the following data structures used by RDBSS:

SRV_CALL

NET_ROOT

V_NET_ROOT

SRV_OPEN

FOBX

If <b>RxDereference</b> is called with any other type of RDBSS data structure, the routine causes the system to ASSERT on checked builds.

If the <b>NodeReferenceCount</b> member is less than 0 after being derefenced (decremented) by <b>RxDereference</b>, then <b>RxDereference</b> causes the system to ASSERT on checked builds. 

If the <b>NodeReferenceCount</b> member decrements to 1 and the <i>LockHoldingState</i> parameter was LHS_ExclusiveLockHeld, the instance of the data structure can be finalized immediately. Otherwise, the instance of the data structure is tagged to be scavenged and finalized later. 




## -see-also

<a href="https://msdn.microsoft.com/866eba91-13b6-4b15-93de-4f627a635c92">The V_NET_ROOT Structure</a>



<a href="https://msdn.microsoft.com/6cf4c6f6-a21f-4919-92b5-2403b650d8d0">The SRV_OPEN Structure</a>



<a href="https://msdn.microsoft.com/f7846343-9af6-4b7f-9c8d-190abb524946">The NET_ROOT Structure</a>



<a href="..\rxprocs\nf-rxprocs-rxreference.md">RxReference</a>



<a href="https://msdn.microsoft.com/9a3bb194-0289-47f4-a5c8-848d8d82cdd7">The SRV_CALL Structure</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-fobx-structure">The FOBX Structure</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxDereference function%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

