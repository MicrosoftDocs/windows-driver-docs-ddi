---
UID: NF:wdm.ClfsMgmtRegisterManagedClient
title: ClfsMgmtRegisterManagedClient function (wdm.h)
description: The ClfsMgmtRegisterManagedClient routine creates a client that will manage a CLFS log.
old-location: kernel\clfsmgmtregistermanagedclient.htm
tech.root: kernel
ms.assetid: 6f450117-9bd2-4021-b8f1-393db5784136
ms.date: 04/30/2018
keywords: ["ClfsMgmtRegisterManagedClient function"]
ms.keywords: ClfsMgmtRegisterManagedClient, ClfsMgmtRegisterManagedClient routine [Kernel-Mode Driver Architecture], Clfs_management_9cd62567-e8c0-4a27-a3fd-153f0cdc9516.xml, kernel.clfsmgmtregistermanagedclient, wdm/ClfsMgmtRegisterManagedClient
f1_keywords:
 - "wdm/ClfsMgmtRegisterManagedClient"
 - "ClfsMgmtRegisterManagedClient"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Clfs.sys
- Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
- ClfsMgmtRegisterManagedClient
targetos: Windows
req.typenames: 
---

# ClfsMgmtRegisterManagedClient function


## -description


The <b>ClfsMgmtRegisterManagedClient</b> routine creates a client that will manage a CLFS log.


## -parameters




### -param LogFile 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a> structure that represents the CLFS log stream that the client created by <b>ClfsMgmtRegisterManagedClient</b> will manage.


### -param RegistrationData 
[in]
An instance of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_clfs_mgmt_client_registration">CLFS_MGMT_CLIENT_REGISTRATION</a> structure that contains the functions that will be used to manage the log.


### -param ClientCookie

The cookie we give back to the caller for future use of the API.




#### - Client [out]

A pointer to the client.


## -returns



The <b>ClfsMgmtRegisterManagedClient</b> routine returns one of the following NTSTATUS values:

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
A client has been created to manage the log.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
CLFS management was not able to create a client to manage the log. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There is insufficient memory to complete the operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An input parameter is invalid.

</td>
</tr>
</table>
 

This routine might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS Values</a>.




## -remarks



The <i>Client</i> parameter that  is provided by the <b>ClfsMgmtRegisterManagedClient</b> routine is a required parameter for other CLFS management functions. You should store this value for later use.

A client application must be ready for its callback routine to be called as soon as it calls the <b>ClfsMgmtRegisterManagedClient</b> routine.

More than one client can register with a log stream.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_clfs_mgmt_client_registration">CLFS_MGMT_CLIENT_REGISTRATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a>
 

 

