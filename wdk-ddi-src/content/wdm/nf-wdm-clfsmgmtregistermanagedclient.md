---
UID: NF:wdm.ClfsMgmtRegisterManagedClient
title: ClfsMgmtRegisterManagedClient function
author: windows-driver-content
description: The ClfsMgmtRegisterManagedClient routine creates a client that will manage a CLFS log.
old-location: kernel\clfsmgmtregistermanagedclient.htm
old-project: kernel
ms.assetid: 6f450117-9bd2-4021-b8f1-393db5784136
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/ClfsMgmtRegisterManagedClient, kernel.clfsmgmtregistermanagedclient, ClfsMgmtRegisterManagedClient, Clfs_management_9cd62567-e8c0-4a27-a3fd-153f0cdc9516.xml, ClfsMgmtRegisterManagedClient routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
apiname:
-	ClfsMgmtRegisterManagedClient
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsMgmtRegisterManagedClient function


## -description


The <b>ClfsMgmtRegisterManagedClient</b> routine creates a client that will manage a CLFS log.


## -syntax


````
NTSTATUS ClfsMgmtRegisterManagedClient(
  _In_  PLOG_FILE_OBJECT               LogFile,
  _In_  PCLFS_MGMT_CLIENT_REGISTRATION RegistrationData,
  _Out_ PCLFS_MGMT_CLIENT              Client
);
````


## -parameters




### -param LogFile [in]

A pointer to a <a href="..\wdm\ns-wdm-_file_object.md">LOG_FILE_OBJECT</a> structure that represents the CLFS log stream that the client created by <b>ClfsMgmtRegisterManagedClient</b> will manage.


### -param RegistrationData [in]

An instance of the <a href="..\wdm\ns-wdm-_clfs_mgmt_client_registration.md">CLFS_MGMT_CLIENT_REGISTRATION</a> structure that contains the functions that will be used to manage the log.


### -param ClientCookie

TBD



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

This routine might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS Values</a>.



## -remarks


The <i>Client</i> parameter that  is provided by the <b>ClfsMgmtRegisterManagedClient</b> routine is a required parameter for other CLFS management functions. You should store this value for later use.

A client application must be ready for its callback routine to be called as soon as it calls the <b>ClfsMgmtRegisterManagedClient</b> routine.

More than one client can register with a log stream.



## -see-also

<a href="..\wdm\ns-wdm-_file_object.md">LOG_FILE_OBJECT</a>

<a href="..\wdm\ns-wdm-_clfs_mgmt_client_registration.md">CLFS_MGMT_CLIENT_REGISTRATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsMgmtRegisterManagedClient routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

