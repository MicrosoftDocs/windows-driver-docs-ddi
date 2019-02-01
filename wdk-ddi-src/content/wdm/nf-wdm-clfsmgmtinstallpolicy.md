---
UID: NF:wdm.ClfsMgmtInstallPolicy
title: ClfsMgmtInstallPolicy function (wdm.h)
description: The ClfsMgmtInstallPolicy routine adds a CLFS_MGMT_POLICY structure to a physical log.
old-location: kernel\clfsmgmtinstallpolicy.htm
tech.root: kernel
ms.assetid: 0a492a86-e732-4302-b35d-9b2a5eb05445
ms.date: 04/30/2018
ms.keywords: ClfsMgmtInstallPolicy, ClfsMgmtInstallPolicy routine [Kernel-Mode Driver Architecture], Clfs_management_44c8b983-a3bb-4fe3-9022-3e669ba5af2b.xml, kernel.clfsmgmtinstallpolicy, wdm/ClfsMgmtInstallPolicy
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
-	ClfsMgmtInstallPolicy
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsMgmtInstallPolicy function


## -description


The <b>ClfsMgmtInstallPolicy</b> routine adds a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541842">CLFS_MGMT_POLICY</a> structure to a physical log.


## -parameters




### -param LogFile [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a> structure that represents the CLFS log that this instance of the <b>CLFS_MGMT_POLICY</b> structure will apply to. The policy applies to all streams within the log, even if a single stream within the log was specified. 


### -param Policy [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541842">CLFS_MGMT_POLICY</a> structure that contains the policy to be installed.


### -param PolicyLength [in]

The length, in bytes, of the structure pointed to by the <i>Policy</i> parameter. 


## -returns



The <b>ClfsMgmtInstallPolicy</b> routine returns one of the following NTSTATUS values:

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
The policy has been installed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
A <b>NULL</b> value was supplied for the <i>LogFile</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
A <b>NULL</b> value was supplied for the <i>Policy</i> parameter. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_3</b></dt>
</dl>
</td>
<td width="60%">
The value of the <i>PolicyLength</i> parameter is less than the size of an instance of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541842">CLFS_MGMT_POLICY</a> structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The <b>PolicyFlags</b> member of the <b>CLFS_MGMT_POLICY_STRUCTURE</b> pointed to by the <i>Policy</i> parameter specifies any flag other than LOG_POLICY_OVERWRITE.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the following conditions is true:

<ul>
<li>
The <i>Policy</i> parameter's <b>Version</b> member is not equal to CLFS_MGMT_POLICY_VERSION.

</li>
<li>
The value of the <i>Policy </i>parameter is equal to <b>ClfsMgmtPolicyInvalid</b>.

</li>
<li>
The <i>Policy</i> parameter's <b>PolicyFlags</b> member specifies any flag other than LOG_POLICY_OVERWRITE.

</li>
</ul>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_LOG_POLICY_ALREADY_INSTALLED</b></dt>
</dl>
</td>
<td width="60%">
The log already has a policy of this type, and the LOG_POLICY_OVERWRITE flag is not set.

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
</table>
 

This routine might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS Values</a>.




## -remarks



Policies are volatile. When all handles to the log are closed, the policies will be lost. You should install policies each time you register the first client.

You should only register a <b>CLFS_MGMT_POLICY</b> structure whose <b>PolicyType</b> member is equal to <b>ClfsMgmtPolicyNewContainerSize</b> before the first container in the log is created. Any subsequent registrations are ignored.

The log policy that is installed applies to the physical log, even if the <i>LogFile</i> parameter specifies a log stream.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541842">CLFS_MGMT_POLICY</a>
 

 

