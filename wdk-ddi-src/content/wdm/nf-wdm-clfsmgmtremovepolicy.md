---
UID: NF:wdm.ClfsMgmtRemovePolicy
title: ClfsMgmtRemovePolicy function (wdm.h)
description: The ClfsMgmtRemovePolicy routine resets a log's CLFS_MGMT_POLICY structure to its default value.
old-location: kernel\clfsmgmtremovepolicy.htm
tech.root: kernel
ms.assetid: 6f0ae6fc-4f2f-4a1a-ac2f-93689f6b7d50
ms.date: 04/30/2018
keywords: ["ClfsMgmtRemovePolicy function"]
ms.keywords: ClfsMgmtRemovePolicy, ClfsMgmtRemovePolicy routine [Kernel-Mode Driver Architecture], Clfs_management_70e3d576-6891-4379-a25b-d880222db235.xml, kernel.clfsmgmtremovepolicy, wdm/ClfsMgmtRemovePolicy
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ClfsMgmtRemovePolicy
 - wdm/ClfsMgmtRemovePolicy
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Clfs.sys
 - Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
 - ClfsMgmtRemovePolicy
---

# ClfsMgmtRemovePolicy function


## -description

The <b>ClfsMgmtRemovePolicy</b> routine resets a log's <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_clfs_mgmt_policy">CLFS_MGMT_POLICY</a> structure to its default value.

## -parameters

### -param LogFile 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a> structure that represents the CLFS log whose policy is being removed.

### -param PolicyType 

[in]
A value of the <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_clfs_mgmt_policy_type">CLFS_MGMT_POLICY_TYPE</a> enumeration that supplies the type of the policy to be removed.

## -returns

The <b>ClfsMgmtRemovePolicy</b> routine returns one of the following NTSTATUS values:

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
CLFS management has removed the requested policy.

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
The value of the <i>PolicyType</i> parameter is not a valid value for the <b>CLFS_MGMT_POLICY_TYPE</b> enumeration.

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
 

This routine might also return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS Values</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_clfs_mgmt_policy">CLFS_MGMT_POLICY</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_clfs_mgmt_policy_type">CLFS_MGMT_POLICY_TYPE</a>