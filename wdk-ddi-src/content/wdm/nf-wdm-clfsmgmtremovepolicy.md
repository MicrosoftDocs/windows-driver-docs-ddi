---
UID: NF:wdm.ClfsMgmtRemovePolicy
title: ClfsMgmtRemovePolicy function
author: windows-driver-content
description: The ClfsMgmtRemovePolicy routine resets a log's CLFS_MGMT_POLICY structure to its default value.
old-location: kernel\clfsmgmtremovepolicy.htm
old-project: kernel
ms.assetid: 6f0ae6fc-4f2f-4a1a-ac2f-93689f6b7d50
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ClfsMgmtRemovePolicy, ClfsMgmtRemovePolicy routine [Kernel-Mode Driver Architecture], kernel.clfsmgmtremovepolicy, Clfs_management_70e3d576-6891-4379-a25b-d880222db235.xml, wdm/ClfsMgmtRemovePolicy
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
-	ClfsMgmtRemovePolicy
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsMgmtRemovePolicy function


## -description


The <b>ClfsMgmtRemovePolicy</b> routine resets a log's <a href="..\wdm\ns-wdm-_clfs_mgmt_policy.md">CLFS_MGMT_POLICY</a> structure to its default value.


## -syntax


````
NTSTATUS ClfsMgmtRemovePolicy(
  _In_ PLOG_FILE_OBJECT      LogFile,
  _In_ CLFS_MGMT_POLICY_TYPE PolicyType
);
````


## -parameters




#### - LogFile [in]

A pointer to a <a href="..\wdm\ns-wdm-_file_object.md">LOG_FILE_OBJECT</a> structure that represents the CLFS log whose policy is being removed.


#### - PolicyType [in]

A value of the <a href="..\wdm\ne-wdm-_clfs_mgmt_policy_type.md">CLFS_MGMT_POLICY_TYPE</a> enumeration that supplies the type of the policy to be removed.


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

This routine might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS Values</a>.



## -see-also

<a href="..\wdm\ns-wdm-_clfs_mgmt_policy.md">CLFS_MGMT_POLICY</a>

<a href="..\wdm\ne-wdm-_clfs_mgmt_policy_type.md">CLFS_MGMT_POLICY_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsMgmtRemovePolicy routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

