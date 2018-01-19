---
UID: NF:ndis.NdisMFlushLog
title: NdisMFlushLog function
author: windows-driver-content
description: NdisMFlushLog clears the log file.
old-location: netvista\ndismflushlog.htm
old-project: netvista
ms.assetid: a681b704-80cc-406a-b60f-31ef5f953164
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisMFlushLog
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMFlushLog (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisMFlushLog (NDIS 5.1)) in Windows   XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMFlushLog
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miniport_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMFlushLog function



## -description
<b>NdisMFlushLog</b> clears the log file.



## -syntax

````
VOID NdisMFlushLog(
  _In_ NDIS_HANDLE LogHandle
);
````


## -parameters

### -param LogHandle [in]

Specifies the handle returned by 
     <a href="..\ndis\nf-ndis-ndismcreatelog.md">NdisMCreateLog</a>.


## -returns
None


## -remarks
<b>NdisMFlushLog</b> resets the position pointers within the log file to the start of the file.

The driver must release any spin lock it is holding before calling 
    <b>NdisMFlushLog</b>.


## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndismcloselog.md">NdisMCloseLog</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcreatelog.md">NdisMCreateLog</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismwritelogdata.md">NdisMWriteLogData</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisreleasespinlock.md">NdisReleaseSpinLock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMFlushLog function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

