---
UID: NF:wdm.ClfsCreateScanContext
title: ClfsCreateScanContext function (wdm.h)
description: The ClfsCreateScanContext routine creates a scan context that can be used to iterate over the containers of a specified CLFS log.
old-location: kernel\clfscreatescancontext.htm
tech.root: kernel
ms.assetid: f3392e43-8463-4d21-9206-34d09f3c7f59
ms.date: 04/30/2018
ms.keywords: ClfsCreateScanContext, ClfsCreateScanContext routine [Kernel-Mode Driver Architecture], Clfs_475944a4-914e-4532-a066-ee7ff9109756.xml, kernel.clfscreatescancontext, wdm/ClfsCreateScanContext
ms.topic: function
f1_keywords:
 - "wdm/ClfsCreateScanContext"
req.header: wdm.h
req.include-header: Wdm.h
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
- ClfsCreateScanContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsCreateScanContext function


## -description


The <b>ClfsCreateScanContext</b> routine creates a scan context that can be used to iterate over the containers of a specified CLFS log.


## -parameters




### -param plfoLog [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a> structure that represents a CLFS stream. The scan context is created for the log that provides the underlying storage for that stream. The caller previously obtained this pointer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-clfscreatelogfile">ClfsCreateLogFile</a>.


### -param cFromContainer [in]

The index of the first container to be scanned. Containers are indexed starting at zero.


### -param cContainers [in]

The number of containers to be scanned with each call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-clfsscanlogcontainers">ClfsScanLogContainers</a>.


### -param eScanMode [in]

 A set of flags that specify whether the scan context is set up for scanning forward or backward and whether the scan context should be reinitialized. The following three flags are available for callers of this routine.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
CLFS_SCAN_FORWARD

</td>
<td>
Set up the scan context for scanning in the forward direction. For example, if container 5 is the most recently scanned container and <i>cContainers</i> is 2, then a forward scan would return descriptors for containers 6 and 7.

</td>
</tr>
<tr>
<td>
CLFS_SCAN_BACKWARD

</td>
<td>
Set up the scan context for scanning in the backward direction. For example, if container 5 is the most recently scanned container and <i>cContainers</i> is 2, then a backward scan would return descriptors for containers 4 and 3.

</td>
</tr>
<tr>
<td>
CLFS_SCAN_INIT

</td>
<td>
Reinitialize the scan context. The next time <b>ClfsScanLogContainers</b> is called, it will behave as if it were being called for the first time after the creation of the scan context.

</td>
</tr>
</table>
 

If <i>pcxScan</i> points to a CLFS_SCAN_CONTEXT structure that is being passed to this routine for the first time, one of the direction flags (CLFS_SCAN_FORWARD or CLFS_SCAN_BACKWARD) must be set. The CLFS_SCAN_INIT flag must not be set.

If <i>pcxScan</i> points to a CLFS_SCAN_CONTEXT structure that has been passed to this routine previously, the CLFS_SCAN_INIT flag must be set. Also, one and only one of the direction flags (CLFS_SCAN_FORWARD or CLFS_SCAN_BACKWARD) must be set.


### -param pcxScan [in, out]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_cls_scan_context">CLFS_SCAN_CONTEXT</a> structure whose members are initialized by this routine. This structure is later passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-clfsscanlogcontainers">ClfsScanLogContainers</a>.


## -returns



<b>ClfsCreateScanContext</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes in Ntstatus.h.




## -remarks



For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-clfsscanlogcontainers">ClfsScanLogContainers</a>
 

 

