---
UID: NF:mrx.RxSetDomainForMailslotBroadcast
title: RxSetDomainForMailslotBroadcast function (mrx.h)
description: Learn more about the RxSetDomainForMailslotBroadcast function.
tech.root: ifsk
ms.date: 10/11/2023
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

**RxSetDomainForMailslotBroadcast** is called by a network mini-redirector driver to set the domain used for mailslot broadcasts if mailslots are supported by the driver.

## -parameters

### -param DomainName [in]

A pointer to a buffer that contains a zero-terminated Unicode string that names the domain to use for mailslots.

## -returns

**RxSetDomainForMailslotBroadcast** returns STATUS_SUCCESS on success or one of the following error values on failure:

| Return code | Description |
| ----------- | ----------- |
| STATUS_INSUFFICIENT_RESOURCES | There were insufficient resources to complete this routine. The memory allocation request failed for nonpaged pool memory to store the domain name. |

## -remarks

A network mini-redirector registers with RDBSS whenever the driver is loaded by the kernel and unregisters with RDBSS when the driver is unloaded. This registration process is a two-way hand shake in which the network mini-redirector informs RDBSS that it has been loaded by calling **RxRegisterMinirdr**, the registration routine exported from RDBSS. RDBSS completes the registration and initialization process by calling **MrxStart**, one of the callback routines exported by the network mini-redirector and passed in as part of the dispatch table to **RxRegisterMinirdr**.

One of the parameters passed to the **RxRegisterMinirdr** routine indicates whether the network mini-redirector supports mailslots. A network mini-redirector would normally call **RxSetDomainForMailslotBroadcast** from the **MrxStart** routine or as part of an external request to start the driver initiated by a file system control (FSCTRL) or an I/O control (IOCTL) request from a user-mode application or service.

## -see-also

[**IoCreateDevice**](../wdm/nf-wdm-iocreatedevice.md)

[**RxRegisterMinirdr**](nf-mrx-rxregisterminirdr.md)

[**RxStartMiniRdr**](nf-mrx-rxstartminirdr.md)

[**RxStopMiniRdr**](nf-mrx-rxstopminirdr.md)

[**RxFillAndInstallFastIoDispatch**](nf-mrx-__rxfillandinstallfastiodispatch.md)
