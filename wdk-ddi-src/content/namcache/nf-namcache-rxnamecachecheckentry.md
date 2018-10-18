---
UID: NF:namcache.RxNameCacheCheckEntry
title: RxNameCacheCheckEntry function
author: windows-driver-content
description: RxNameCacheCheckEntry checks a name cache entry for validity. A valid entry means that the lifetime has not expired and the MRxContext parameter passes the equality check.
old-location: ifsk\rxnamecachecheckentry.htm
tech.root: ifsk
ms.assetid: 75df65bc-2309-40d6-8e1d-154e72ad0f23
ms.date: 4/16/2018
ms.keywords: RxNameCacheCheckEntry, RxNameCacheCheckEntry function [Installable File System Drivers], ifsk.rxnamecachecheckentry, namcache/RxNameCacheCheckEntry, rxref_703b5e6a-4904-4402-8905-bc1dd2ed1c9e.xml
ms.topic: function
req.header: namcache.h
req.include-header: Namcache.h
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
-	namcache.h
api_name:
-	RxNameCacheCheckEntry
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxNameCacheCheckEntry function


## -description


<b>RxNameCacheCheckEntry</b> checks a name cache entry for validity. A valid entry means that the lifetime has not expired and the <i>MRxContext</i> parameter passes the equality check.


## -parameters




### -param NameCache [in]

A pointer to the NAME_CACHE structure to check.


### -param MRxContext [in]

A value of context supplied by the network mini-redirector for equality checking when making a valid entry check. 


## -returns



<b>RxNameCacheCheckEntry </b>returns one of the possible enumeration values defined for <b>RX_NC_CHECK_STATUS</b>:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>RX_NC_SUCCESS </b></dt>
</dl>
</td>
<td width="60%">
The check was successful and the entry is valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>RX_NC_TIME_EXPIRED</b></dt>
</dl>
</td>
<td width="60%">
The check failed because the lifetime has expired.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>RX_NC_MRXCTX_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The check failed because <i>MRxContext</i> failed equality checking.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554552">RxNameCacheActivateEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554565">RxNameCacheCreateEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554569">RxNameCacheExpireEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554570">RxNameCacheExpireEntryWithShortName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554573">RxNameCacheFetchEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554575">RxNameCacheFinalize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554579">RxNameCacheFreeEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554586">RxNameCacheInitialize</a>
 

 

