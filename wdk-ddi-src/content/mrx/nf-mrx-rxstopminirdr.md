---
UID: NF:mrx.RxStopMinirdr
title: RxStopMinirdr function (mrx.h)
description: RxStopMinirdr is called to stop a network mini-redirector that has previously been started.
old-location: ifsk\rxstopminirdr.htm
tech.root: ifsk
ms.assetid: 059d2a99-f4da-45f1-8d91-0e57930595d2
ms.date: 04/16/2018
keywords: ["RxStopMinirdr function"]
ms.keywords: RxStopMinirdr, RxStopMinirdr function [Installable File System Drivers], ifsk.rxstopminirdr, mrx/RxStopMinirdr, rxref_3ec6b643-e13c-4aa6-879b-fdb2076e549d.xml
f1_keywords:
 - "mrx/RxStopMinirdr"
 - "RxStopMinirdr"
req.header: mrx.h
req.include-header: Mrx.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- mrx.h
api_name:
- RxStopMinirdr
targetos: Windows
req.typenames: 
---

# RxStopMinirdr function


## -description


<b>RxStopMinirdr</b> is called to stop a network mini-redirector that has previously been started. As part of <b>RxStopMinirdr</b>, RDBSS will also de-register the network mini-redirector driver as a universal naming convention (UNC) provider with the Multiple UNC Provider (MUP) if the driver indicates support for UNC names.


## -parameters




### -param RxContext 
[in]
A pointer to the RX_CONTEXT structure to use to get the device object and determine if this is a file system process. 


### -param PostToFsp 
[out]
A pointer to a logical value that is set to <b>TRUE</b> on return if the request must be posted for later processing by the file system process. 


## -returns



<b>RxStopMinirdr</b> returns STATUS_SUCCESS if the stop sequence was successful or one of the following error values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The stop sequence for RDBSS and network mini-redirectors must be completed in the context of the file system process. If the call to <b>RxStopMinirdr</b> comes from a different process (a user-mode request, for example), then the request will be posted for later processing and STATUS_PENDING will be returned. This error can also be returned if certain internal RDBSS locks cannot be acquired without waiting.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REDIRECTOR_HAS_OPEN_HANDLES</b></dt>
</dl>
</td>
<td width="60%">
The network mini-redirector has open handles and cannot be stopped at this time. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REDIRECTOR_STOPPED</b></dt>
</dl>
</td>
<td width="60%">
The network mini-redirector was already stopped. 

</td>
</tr>
</table>
 




## -remarks



When a stop request is issued to RDBSS, there may be ongoing requests in the RDBSS. Some of the requests can be canceled while the remaining requests need to be processed to completion.

There are a number of strategies that can be employed to close down the RDBSS. Currently, the most conservative approach is employed. The cancellation of those operations that can be canceled and the stop operation is held back until the remaining requests run through to completion.

The RDBSS <b>RxStopMinirdr </b>is usually called as a result of an FSCTL or IOCTL request from a user-mode application or service to stop the network mini-redirector, although this call could also be made from the network mini-redirector or as part of shutdown processing by the operating system. 

Once a call to <b>RxStopMinirdr</b> is issued, the only operations allowed by RDBSS and passed to the network mini-redirector are rerquests for the following I/O request packets:

<ul>
<li>
IRP_MJ_CLEANUP

</li>
<li>
IRP_MJ_CLOSE

</li>
</ul>
The stop sequence for RDBSS and the network mini-redirector must be completed in the context of the file system process. If the call to <b>RxStopMinirdr</b> comes from a different process (a user-mode request, for example), then the request must be posted for later processing and STATUS_PENDING will be returned. In this case, the effective user ID (the logon ID) of the caller is saved in the <b>FsdUid</b> member of the <i>RxContext</i> parameter. In addition, If certain internal RDBSS locks cannot be obtained without waiting, STATUS_PENDING is returned and <i>PostToFsp</i> is set to <b>TRUE</b>. When STATUS_PENDING is returned, then <b>RxStopMinirdr</b> will be posted for later processing by a file system process and completed. 

If a network mini-redirector indicates support for UNC when registering with RDBSS (the <i>Controls</i> parameter to <b>RxRegisterMinirdr</b>), then <b>RxStopMinirdr</b> will try to de-register the <i>DeviceName</i> of the network mini-redirector as a UNC provider with MUP (calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545865">FsRtlDeregisterUncProvider</a> on behalf of the network mini-redirector). <b>RxStopMinirdr</b> also de-registers the file system with the I/O manager (calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfilesystem">IoUnregisterFileSystem</a>) on behalf of the network mini-redirector).

The <b>RxStopMinirdr</b> routine then calls the network mini-redirector <b>MrxStop</b> callback routine if this routine is implemented. If there are no active FCBs remaining, STATUS_SUCCESS is returned. If there are some remaining active FCBs, STATUS_REDIRECTOR_HAS_OPEN_HANDLES is returned. In either case, the RDBSS dispatcher for the redrector is spun down and the internal state of the network mini-redirector in RDBSS is set to RDBSS_STARTABLE. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545865">FsRtlDeregisterUncProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iounregisterfilesystem">IoUnregisterFileSystem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nf-mrx-rxregisterminirdr">RxRegisterMinirdr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nf-mrx-rxstartminirdr">RxStartMiniRdr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxstruc/nf-rxstruc-rxunregisterminirdr">RxUnregisterMinirdr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nf-mrx-rxpunregisterminirdr">RxpUnregisterMinirdr</a>
 

 

