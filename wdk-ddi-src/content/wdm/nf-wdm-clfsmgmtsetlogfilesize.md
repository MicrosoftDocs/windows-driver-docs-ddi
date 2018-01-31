---
UID: NF:wdm.ClfsMgmtSetLogFileSize
title: ClfsMgmtSetLogFileSize function
author: windows-driver-content
description: The ClfsMgmtSetLogFileSize routine adds containers to a log or deletes containers from a log.
old-location: kernel\clfsmgmtsetlogfilesize.htm
old-project: kernel
ms.assetid: 76588bdd-ceb8-4c8b-bcd7-23184feacf86
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/ClfsMgmtSetLogFileSize, ClfsMgmtSetLogFileSize routine [Kernel-Mode Driver Architecture], ClfsMgmtSetLogFileSize, kernel.clfsmgmtsetlogfilesize, Clfs_management_a4f0865a-5c4b-411b-a8a5-349b49c1528b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows Server 2003 R2 and Windows Vista.
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
-	ClfsMgmtSetLogFileSize
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsMgmtSetLogFileSize function


## -description


The <b>ClfsMgmtSetLogFileSize</b> routine adds containers to a log or deletes containers from a log.


## -syntax


````
NTSTATUS ClfsMgmtSetLogFileSize(
  _In_     PLOG_FILE_OBJECT                     LogFile,
  _In_     PULONGLONG                           NewSizeInContainers,
  _Out_    PULONGLONG                           ResultingSizeInContainers,
  _In_opt_ PCLFS_SET_LOG_SIZE_COMPLETE_CALLBACK CompletionRoutine,
  _In_opt_ PVOID                                CompletionRoutineData
);
````


## -parameters




#### - LogFile [in]

A pointer to a <a href="..\wdm\ns-wdm-_file_object.md">LOG_FILE_OBJECT</a> structure that represents the CLFS log, or a stream within the log, to which containers are being added or deleted.


#### - NewSizeInContainers [in]

A pointer to the requested log size. The caller sets this parameter to one of the following values.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>0</td>
<td>
Enforce the minimum size policy. For more information about this policy, see <a href="..\wdm\nf-wdm-clfsmgmtinstallpolicy.md">ClfsMgmtInstallPolicy</a>.

If a minimum size policy is not installed, one of the following occurs:

<ul>
<li>If the log currently has less than 2 containers, the log will be expanded to a size of 2 containers.</li>
<li>If the log currently has 2 or more containers, no changes are made and the call succeeds.</li>
</ul>
If a minimum size policy is installed, one of the following occurs:

<ul>
<li>If the log currently has less than the minimum number of containers specified by the minimum size policy, the log expands to the policy-specified minimum number of containers.</li>
<li>If the number of containers in the log is greater than or equal to the minimum number of containers specified by the minimum size policy, no changes are made and the call succeeds with no error.</li>
</ul>
</td>
</tr>
<tr>
<td>1</td>
<td>Invalid value. The call fails and returns STATUS_INVALID_VALUE.</td>
</tr>
<tr>
<td>2 to 1023</td>
<td>
The desired size of the log, expressed as the number of containers.

If this number is smaller than the minimum number of containers specified by the installed policy, the call fails with ERROR_COULD_NOT_RESIZE_LOG.

If this number is larger than the maximum number of containers specified by the installed policy, the log expands only as far as the policy-specified maximum number of containers, and the call succeeds with no error.

</td>
</tr>
<tr>
<td>1024 to MAXULONGLONG</td>
<td>
If no maximum size policy is installed, the call fails and returns ERROR_LOG_POLICY_CONFLICT.

If a maximum size policy is installed, the log expands to the maximum number of containers specified by the maximum size policy and the call succeeds with no error.

</td>
</tr>
</table> 

To determine the actual log size, which might be different from the requested size, use the <i>ResultingSizeInContainers</i> parameter.


#### - ResultingSizeInContainers [out]

A pointer to the resulting log size. If successful, the routine writes the actual size of the log, expressed as the number of containers in the log, to the location pointed to by this parameter.


#### - CompletionRoutine [in, optional]

 Not used.  Set to NULL.


#### - CompletionRoutineData [in, optional]

 Not used. Set to NULL.


## -returns


The <b>ClfsMgmtSetLogFileSize</b> routine returns one of the following NTSTATUS values:
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
The log file size has been set. The <i>ResultingSizeInContainers</i> parameter contains the current size of the log.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
CLFS management was not able to set the log file size.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
The value of the <i>LogFile</i> parameter is <b>NULL</b>, or the contents of the <i>NewSizeInContainers</i> parameter is 1.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The value of the <i>NewSizeInContainers</i> parameter is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_LOG_POLICY_INVALID</b></dt>
</dl>
</td>
<td width="60%">
There is a conflict between the maximum size and minimum size policies for the log.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_COULD_NOT_RESIZE_LOG</b></dt>
</dl>
</td>
<td width="60%">
CLFS management could not delete enough containers to reach <i>NewSizeInContainers</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_LOG_POLICY_CONFLICT</b></dt>
</dl>
</td>
<td width="60%">
CLFS management could not add enough containers to the log to reach <i>NewSizeInContainers</i>. This might be due to a conflict with a policy that the client set.

</td>
</tr>
</table> 

This routine might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS Values</a>.



## -remarks


The <b>ClfsMgmtSetLogFileSize</b> routine is typically used only when a client starts or stops. Do not call the <b>ClfsMgmtSetLogFileSize</b> routine from within your <a href="..\wdm\nc-wdm-pclfs_client_advance_tail_callback.md">ClfsAdvanceTailCallback</a> function.



## -see-also

<a href="..\wdm\nf-wdm-clfsmgmtinstallpolicy.md">ClfsMgmtInstallPolicy</a>

<a href="..\wdm\ne-wdm-_clfs_mgmt_policy_type.md">CLFS_MGMT_POLICY_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsMgmtSetLogFileSize routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

