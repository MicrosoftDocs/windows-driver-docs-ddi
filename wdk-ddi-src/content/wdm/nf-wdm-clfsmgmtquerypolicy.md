---
UID: NF:wdm.ClfsMgmtQueryPolicy
title: ClfsMgmtQueryPolicy function (wdm.h)
description: The ClfsMgmtQueryPolicy routine retrieves a specific CLFS_MGMT_POLICY structure for a log.
old-location: kernel\clfsmgmtquerypolicy.htm
tech.root: kernel
ms.assetid: c9cc9124-ee15-40df-b149-a9f3b26d7c24
ms.date: 04/30/2018
keywords: ["ClfsMgmtQueryPolicy function"]
ms.keywords: ClfsMgmtQueryPolicy, ClfsMgmtQueryPolicy routine [Kernel-Mode Driver Architecture], Clfs_management_6f3ccba5-05e5-4022-9849-220aeefbde77.xml, kernel.clfsmgmtquerypolicy, wdm/ClfsMgmtQueryPolicy
f1_keywords:
 - "wdm/ClfsMgmtQueryPolicy"
 - "ClfsMgmtQueryPolicy"
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
- ClfsMgmtQueryPolicy
targetos: Windows
req.typenames: 
---

# ClfsMgmtQueryPolicy function


## -description


The <b>ClfsMgmtQueryPolicy</b> routine retrieves a specific <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_clfs_mgmt_policy">CLFS_MGMT_POLICY</a> structure for a log.


## -parameters




### -param LogFile [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a> structure that represents the CLFS log whose policy is being retrieved.


### -param PolicyType [in]

A value of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_clfs_mgmt_policy_type">CLFS_MGMT_POLICY_TYPE</a> enumeration that identifies the type of policy to be retrieved.


### -param Policy [out]

An instance of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_clfs_mgmt_policy">CLFS_MGMT_POLICY</a> structure that contains the policy.


### -param PolicyLength [out]

The length of the <i>Policy</i> parameter.


## -returns



The <b>ClfsMgmtQueryPolicy</b> routine returns one of the following NTSTATUS values:

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
CLFS management has retrieved the requested policy.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
CLFS management was not able to process the request.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The value of the <i>PolicyType</i> parameter is not valid for the <b>CLFS_MGMT_POLICY_TYPE</b> enumeration.

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
The value of the <i>PolicyLength</i> parameter is less than the size of an instance of the <b>CLFS_MGMT_POLICY</b> structure.

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
<dt><b>STATUS_LOG_POLICY_NOT_INSTALLED</b></dt>
</dl>
</td>
<td width="60%">
No policy of this type has been registered for the log file.

</td>
</tr>
</table>
 

This routine might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS Values</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_clfs_mgmt_policy">CLFS_MGMT_POLICY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_clfs_mgmt_policy_type">CLFS_MGMT_POLICY_TYPE</a>
 

 

