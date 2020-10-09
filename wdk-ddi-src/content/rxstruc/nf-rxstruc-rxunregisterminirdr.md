---
UID: NF:rxstruc.RxUnregisterMinirdr
title: RxUnregisterMinirdr function (rxstruc.h)
description: RxUnregisterMinirdr is an inline routine called by a network mini-redirector driver to de-register the driver with RDBSS and remove the registration information from the internal RDBSS registration table.
old-location: ifsk\rxunregisterminirdr.htm
tech.root: ifsk
ms.assetid: 090e5fc5-a0cf-4df2-b9b9-abaf4833aef7
ms.date: 04/16/2018
keywords: ["RxUnregisterMinirdr function"]
ms.keywords: RxUnregisterMinirdr, RxUnregisterMinirdr routine [Installable File System Drivers], ifsk.rxunregisterminirdr, rxref_5c58f656-5d6a-46db-9c7e-f3331e48a66a.xml, rxstruc/RxUnregisterMinirdr
req.header: rxstruc.h
req.include-header: Rxstruc.h, Mrx.h
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
 - RxUnregisterMinirdr
 - rxstruc/RxUnregisterMinirdr
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rxstruc.h
api_name:
 - RxUnregisterMinirdr
---

# RxUnregisterMinirdr function


## -description

<b>RxUnregisterMinirdr</b> is an inline routine called by a network mini-redirector driver to de-register the driver with RDBSS and remove the registration information from the internal RDBSS registration table.

## -parameters

### -param RxDeviceObject 

[in]
A pointer to the RDBSS device object for this network redirector.

## -remarks

<b>RxUnregisterMinirdr</b> is an inline routine defined in <i>rxstruc.h</i> that de-registers the driver with RDBSS and removes the registration information from the internal RDBSS registration table. If name tables were initialized, then these tables will be finalized for release. Any outstanding asynchronous requests to the network mini-redirector are spun down, and any worker threads associated with the redirector are spun down. <b>RxUnregisterMinirdr</b> also tries to remove the device object from the system by calling <b>IoDeleteDevice</b>.

Typically, the <b>RxUnregisterMinirdr </b>routine is called as a result of an FSCTL or IOCTL request from a user-mode application or service to unload the network mini-redirector, although this call could also be made from the network mini-redirector or as part of shutdown processing by the operating system or as a result of a failure in the <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine.

Note that the inline routine, <b>RxUnregisterMinirdr</b>, is the preferred way to unregister a driver with RDBSS. The <b>RxUnregisterMinirdr</b> inline routine calls <b>RxpUnregisterMinirdr</b>, but then also decrements the object reference to the RDBSS device object so that this object can be released by the system.

## -see-also

<a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iodeletedevice">IoDeleteDevice</a>



<a href="/windows-hardware/drivers/ddi/mrx/nf-mrx-rxregisterminirdr">RxRegisterMinirdr</a>



<a href="/windows-hardware/drivers/ddi/mrx/nf-mrx-rxstartminirdr">RxStartMiniRdr</a>



<a href="/windows-hardware/drivers/ddi/mrx/nf-mrx-rxstopminirdr">RxStopMiniRdr</a>



<a href="/windows-hardware/drivers/ddi/mrx/nf-mrx-rxpunregisterminirdr">RxpUnregisterMinirdr</a>