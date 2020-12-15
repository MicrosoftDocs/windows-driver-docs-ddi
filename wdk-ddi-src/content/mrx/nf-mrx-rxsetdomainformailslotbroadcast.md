---
UID: NF:mrx.RxSetDomainForMailslotBroadcast
title: RxSetDomainForMailslotBroadcast function (mrx.h)
description: RxSetDomainForMailslotBroadcast is called by a network mini-redirector driver to set the domain used for mailslot broadcasts if mailslots are supported by the driver.
old-location: ifsk\rxsetdomainformailslotbroadcast.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RxSetDomainForMailslotBroadcast function"]
ms.keywords: RxSetDomainForMailslotBroadcast, RxSetDomainForMailslotBroadcast function [Installable File System Drivers], ifsk.rxsetdomainformailslotbroadcast, mrx/RxSetDomainForMailslotBroadcast, rxref_d342ef48-ef62-4186-97ea-d974bc4bf596.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RxSetDomainForMailslotBroadcast
 - mrx/RxSetDomainForMailslotBroadcast
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mrx.h
api_name:
 - RxSetDomainForMailslotBroadcast
---

# RxSetDomainForMailslotBroadcast function


## -description

<b>RxSetDomainForMailslotBroadcast</b> is called by a network mini-redirector driver to set the domain used for mailslot broadcasts if mailslots are supported by the driver.

## -parameters

### -param DomainName 

[in]
A pointer to a buffer that contains a zero-terminated Unicode string that names the domain to use for mailslots.

## -returns

<b>RxSetDomainForMailslotBroadcast</b> returns STATUS_SUCCESS on success or one of the following error values on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There were insufficient resources to complete this routine. The memory allocation request failed for nonpaged pool memory to store the domain name.

</td>
</tr>
</table>

## -remarks

A network mini-redirector registers with RDBSS whenever the driver is loaded by the kernel and unregisters with RDBSS when the driver is unloaded. This registration process is a two-way hand shake in which the network mini-redirector informs RDBSS that it has been loaded by calling <b>RxRegisterMinirdr</b>, the registration routine exported from RDBSS. RDBSS completes the registration and initialization process by calling <b>MrxStart</b>, one of the callback routines exported by the network mini-redirector and passed in as part of the dispatch table to <b>RxRegisterMinirdr</b>.

One of the parameters passed to the <b>RxRegisterMinirdr</b> routine indicates whether the network mini-redirector supports mailslots. A network mini-redirector would normally call <b>RxSetDomainForMailslotBroadcast</b> from the <b>MrxStart</b> routine or as part of an external request to start the driver initiated by a file system control (FSCTRL) or an I/O control (IOCTL) request from a user-mode application or service.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocreatedevice">IoCreateDevice</a>



<a href="/windows-hardware/drivers/ddi/mrx/nf-mrx-rxregisterminirdr">RxRegisterMinirdr</a>



<a href="/windows-hardware/drivers/ddi/mrx/nf-mrx-rxstartminirdr">RxStartMinirdr</a>



<a href="/windows-hardware/drivers/ddi/mrx/nf-mrx-rxstopminirdr">RxStopMinirdr</a>



<a href="/windows-hardware/drivers/ddi/mrx/nf-mrx-__rxfillandinstallfastiodispatch">__RxFillAndInstallFastIoDispatch</a>
