---
UID: NF:prefix.RxPrefixTableLookupName
title: RxPrefixTableLookupName function
author: windows-driver-content
description: RxPrefixTableLookupName looks up a name in a prefix table used to catalog SRV_CALL, NET_ROOT, and V_NET_ROOT names and converts the underlying pointer to a structure that contains the name.
old-location: ifsk\rxprefixtablelookupname.htm
old-project: ifsk
ms.assetid: 20d61d23-4151-4a23-8963-6e38a08f391e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: rxref_e46fe04e-07a6-4733-936e-e70a51009618.xml, prefix/RxPrefixTableLookupName, RxPrefixTableLookupName, ifsk.rxprefixtablelookupname, RxPrefixTableLookupName function [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: prefix.h
req.include-header: Prefix.h
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
-	prefix.h
apiname:
-	RxPrefixTableLookupName
product: Windows
targetos: Windows
req.typenames: SHIMOPTS, *PSHIMOPTS
req.product: Windows 10 or later.
---

# RxPrefixTableLookupName function


## -description


<b>RxPrefixTableLookupName</b> looks up a name in a prefix table used to catalog SRV_CALL, NET_ROOT, and V_NET_ROOT names and converts the underlying pointer to a structure that contains the name.


## -syntax


````
PVOID RxPrefixTableLookupName(
  _In_  PRX_PREFIX_TABLE  ThisTable,
  _In_  PUNICODE_STRING   CanonicalName,
  _Out_ PUNICODE_STRING   RemainingName,
  _In_  PRX_CONNECTION_ID RxConnectionId
);
````


## -parameters




### -param ThisTable [in]

A pointer to the RX_PREFIX_TABLE structure in which to look.


### -param CanonicalName [in]

A pointer to the Unicode string name to look up.


### -param RemainingName [out]

A pointer to the Unicode string name of the portion of the name that was unmatched.


### -param ConnectionId

TBD



#### - RxConnectionId [in]

An optional parameter that represents a pointer to the RX_CONNECTION_ID to be used.


## -returns


<b>RxPrefixTableLookupName</b> returns a pointer to the node that was found if a match is found. If no match is found, <b>RxPrefixTableLookupName</b> returns a <b>NULL</b> pointer. 



## -remarks


This routine is used internally by RDBSS in response to a call from MUP to claim a name or form the create path for a NET_ROOT or V_NET_ROOT structure. The <b>RxPrefixTableLookupName</b> routine can also be used by network mini-redirectors as long as the appropriate lock is acquired before accessing the table, and the lock is released when work is completed. The normal use by a driver would be as follows:
<ul>
<li>
Acquire a shared lock by calling <b>RxpAcquirePrefixTableLockShared</b>.

</li>
<li>
Look up a name by calling <b>RxPrefixTableLookupName</b>.

</li>
<li>
Release the shared lock by calling <b>RxpReleasePrefixTableLock</b>.

</li>
</ul>Note that if a match is found, the reference count on the found node will be incremented. 

On checked builds, <b>RxPrefixTableLookupName</b> causes the system to ASSERT if the length of the <i>CanonicalName</i> string is not greater than zero.



## -see-also

<a href="..\prefix\nf-prefix-rxpacquireprefixtablelockexclusive.md">RxpAcquirePrefixTableLockExclusive</a>

<a href="..\prefix\nf-prefix-rxpreleaseprefixtablelock.md">RxpReleasePrefixTableLock</a>

<a href="..\prefix\nf-prefix-rxpacquireprefixtablelockshared.md">RxpAcquirePrefixTableLockShared</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxPrefixTableLookupName function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

