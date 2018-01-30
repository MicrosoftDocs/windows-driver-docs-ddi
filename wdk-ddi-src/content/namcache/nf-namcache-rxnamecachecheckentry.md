---
UID: NF:namcache.RxNameCacheCheckEntry
title: RxNameCacheCheckEntry function
author: windows-driver-content
description: RxNameCacheCheckEntry checks a name cache entry for validity. A valid entry means that the lifetime has not expired and the MRxContext parameter passes the equality check.
old-location: ifsk\rxnamecachecheckentry.htm
old-project: ifsk
ms.assetid: 75df65bc-2309-40d6-8e1d-154e72ad0f23
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: namcache/RxNameCacheCheckEntry, RxNameCacheCheckEntry function [Installable File System Drivers], RxNameCacheCheckEntry, rxref_703b5e6a-4904-4402-8905-bc1dd2ed1c9e.xml, ifsk.rxnamecachecheckentry
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	namcache.h
apiname:
-	RxNameCacheCheckEntry
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# RxNameCacheCheckEntry function


## -description


<b>RxNameCacheCheckEntry</b> checks a name cache entry for validity. A valid entry means that the lifetime has not expired and the <i>MRxContext</i> parameter passes the equality check.


## -syntax


````
RX_NC_CHECK_STATUS RxNameCacheCheckEntry(
  _In_ PNAME_CACHE NameCache,
  _In_ ULONG       MRxContext
);
````


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

<a href="..\namcache\nf-namcache-rxnamecachefreeentry.md">RxNameCacheFreeEntry</a>

<a href="..\namcache\nf-namcache-rxnamecacheexpireentrywithshortname.md">RxNameCacheExpireEntryWithShortName</a>

<a href="..\namcache\nf-namcache-rxnamecacheinitialize.md">RxNameCacheInitialize</a>

<a href="..\namcache\nf-namcache-rxnamecacheactivateentry.md">RxNameCacheActivateEntry</a>

<a href="..\namcache\nf-namcache-rxnamecacheexpireentry.md">RxNameCacheExpireEntry</a>

<a href="..\namcache\nf-namcache-rxnamecachefinalize.md">RxNameCacheFinalize</a>

<a href="..\namcache\nf-namcache-rxnamecachefetchentry.md">RxNameCacheFetchEntry</a>

<a href="..\namcache\nf-namcache-rxnamecachecreateentry.md">RxNameCacheCreateEntry</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxNameCacheCheckEntry function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

