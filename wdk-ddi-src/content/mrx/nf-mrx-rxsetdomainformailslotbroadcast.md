---
UID: NF:mrx.RxSetDomainForMailslotBroadcast
title: RxSetDomainForMailslotBroadcast function
author: windows-driver-content
description: RxSetDomainForMailslotBroadcast is called by a network mini-redirector driver to set the domain used for mailslot broadcasts if mailslots are supported by the driver.
old-location: ifsk\rxsetdomainformailslotbroadcast.htm
old-project: ifsk
ms.assetid: 22f5e525-bdf8-4047-9b77-6523cb59f090
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxSetDomainForMailslotBroadcast, rxref_d342ef48-ef62-4186-97ea-d974bc4bf596.xml, RxSetDomainForMailslotBroadcast function [Installable File System Drivers], mrx/RxSetDomainForMailslotBroadcast, ifsk.rxsetdomainformailslotbroadcast
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	mrx.h
apiname:
-	RxSetDomainForMailslotBroadcast
product: Windows
targetos: Windows
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---

# RxSetDomainForMailslotBroadcast function


## -description


<b>RxSetDomainForMailslotBroadcast</b> is called by a network mini-redirector driver to set the domain used for mailslot broadcasts if mailslots are supported by the driver. 


## -syntax


````
NTSTATUS RxSetDomainForMailslotBroadcast(
  _In_ PUNICODE_STRING DomainName
);
````


## -parameters




### -param DomainName [in]

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

<a href="..\mrx\nf-mrx-rxregisterminirdr.md">RxRegisterMinirdr</a>



<a href="..\mrx\nf-mrx-rxstartminirdr.md">RxStartMinirdr</a>



<a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a>



<a href="..\mrx\nf-mrx-__rxfillandinstallfastiodispatch.md">__RxFillAndInstallFastIoDispatch</a>



<a href="..\mrx\nf-mrx-rxstopminirdr.md">RxStopMinirdr</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxSetDomainForMailslotBroadcast function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

