---
UID: NF:wdm.ClfsMgmtDeregisterManagedClient
title: ClfsMgmtDeregisterManagedClient function
description: The ClfsMgmtDeregisterManagedClient routine removes the connection between a client and a log, so that the client no longer manages the log.
old-location: kernel\clfsmgmtderegistermanagedclient.htm
tech.root: kernel
ms.assetid: 5dee3b70-9c8d-420d-86f9-9795b4d8b1e8
ms.date: 04/30/2018
ms.keywords: ClfsMgmtDeregisterManagedClient, ClfsMgmtDeregisterManagedClient routine [Kernel-Mode Driver Architecture], Clfs_management_6a802f4a-8157-42c8-8eda-740a1207714a.xml, kernel.clfsmgmtderegistermanagedclient, wdm/ClfsMgmtDeregisterManagedClient
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
-	ClfsMgmtDeregisterManagedClient
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsMgmtDeregisterManagedClient function


## -description


The <b>ClfsMgmtDeregisterManagedClient</b> routine removes the connection between a client and a log, so that the client no longer manages the log.


## -parameters




### -param ClientCookie

The cookie we give back to the caller for future use of the API.




#### - Client [in]

A pointer to the client. This is the value that was obtained through a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541642">ClfsMgmtRegisterManagedClient</a> routine.


## -returns



The <b>ClfsMgmtDeregisterManagedClient</b> routine returns one of the following NTSTATUS values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The client is no longer associated with the log.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
CLFS management was not able to deregister the client.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A <b>NULL</b> value was supplied for the <i>Client</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
The value that  was supplied for the <i>Client</i> parameter does not represent a valid client.

</td>
</tr>
</table>
 




## -remarks



After calling the <b>ClfsMgmtDeregisterManagedClient</b> routine, a client's callback functions will no longer be invoked.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541642">ClfsMgmtRegisterManagedClient</a>
 

 

