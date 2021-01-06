---
UID: NF:wdm.ClfsMgmtTailAdvanceFailure
title: ClfsMgmtTailAdvanceFailure function (wdm.h)
description: The ClfsMgmtTailAdvanceFailure routine notifies CLFS management that the client could not advance the log's tail.
old-location: kernel\clfsmgmttailadvancefailure.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ClfsMgmtTailAdvanceFailure function"]
ms.keywords: ClfsMgmtTailAdvanceFailure, ClfsMgmtTailAdvanceFailure routine [Kernel-Mode Driver Architecture], Clfs_management_6512b59a-78e2-4b01-ba4f-00b099c2c53f.xml, kernel.clfsmgmttailadvancefailure, wdm/ClfsMgmtTailAdvanceFailure
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ClfsMgmtTailAdvanceFailure
 - wdm/ClfsMgmtTailAdvanceFailure
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Clfs.sys
 - Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
 - ClfsMgmtTailAdvanceFailure
---

# ClfsMgmtTailAdvanceFailure function


## -description

The <b>ClfsMgmtTailAdvanceFailure</b> routine notifies CLFS management that the client could not advance the log's tail.

## -parameters

### -param Client 

[in]
A pointer to the client. This is the value that was obtained through a call to the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsmgmtregistermanagedclient">ClfsMgmtRegisterManagedClient</a> routine.

### -param Reason 

[in]
A value that indicates why the log's tail could not be advanced.

## -returns

The <b>ClfsMgmtTailAdvanceFailure</b> routine returns one of the following NTSTATUS values:

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
CLFS management has processed the notification that the log's tail could not be advanced.

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

If a client cannot advance its log's tail to or beyond the requested LSN, then the client must call the <b>ClfsMgmtTailAdvanceFailure</b> routine to indicate that it is not able to advance its tail. Until the client either moves its tail as requested or calls the <b>ClfsMgmtTailAdvanceFailure</b> routine, the client will not receive any further requests to move its tail.

The value of the <i>Reason</i> parameter is passed back to the client as the value of the <i>OperationStatus</i> parameter when the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_lff_handler_complete_callback">ClfsLogGrowthCompleteCallback</a> function is invoked.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-clfsmgmtregistermanagedclient">ClfsMgmtRegisterManagedClient</a>
