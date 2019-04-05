---
UID: NF:prefix.RxPrefixTableLookupName
title: RxPrefixTableLookupName function (prefix.h)
description: RxPrefixTableLookupName looks up a name in a prefix table used to catalog SRV_CALL, NET_ROOT, and V_NET_ROOT names and converts the underlying pointer to a structure that contains the name.
old-location: ifsk\rxprefixtablelookupname.htm
tech.root: ifsk
ms.assetid: 20d61d23-4151-4a23-8963-6e38a08f391e
ms.date: 04/16/2018
ms.keywords: RxPrefixTableLookupName, RxPrefixTableLookupName function [Installable File System Drivers], ifsk.rxprefixtablelookupname, prefix/RxPrefixTableLookupName, rxref_e46fe04e-07a6-4733-936e-e70a51009618.xml
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
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- prefix.h
api_name:
- RxPrefixTableLookupName
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxPrefixTableLookupName function


## -description


<b>RxPrefixTableLookupName</b> looks up a name in a prefix table used to catalog SRV_CALL, NET_ROOT, and V_NET_ROOT names and converts the underlying pointer to a structure that contains the name.


## -parameters




### -param ThisTable [in]

A pointer to the RX_PREFIX_TABLE structure in which to look.


### -param CanonicalName [in]

A pointer to the Unicode string name to look up.


### -param RemainingName [out]

A pointer to the Unicode string name of the portion of the name that was unmatched.


### -param ConnectionId

<p>An optional parameter that represents a pointer to the RX_CONNECTION_ID to be used.</p>




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
</ul>
Note that if a match is found, the reference count on the found node will be incremented. 

On checked builds, <b>RxPrefixTableLookupName</b> causes the system to ASSERT if the length of the <i>CanonicalName</i> string is not greater than zero.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554595">RxpAcquirePrefixTableLockExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554598">RxpAcquirePrefixTableLockShared</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554637">RxpReleasePrefixTableLock</a>
 

 

