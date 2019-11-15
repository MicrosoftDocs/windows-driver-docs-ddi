---
UID: NF:mrx.RxpUnregisterMinirdr
title: RxpUnregisterMinirdr function (mrx.h)
description: RxpUnregisterMinirdr is called by a network mini-redirector driver to de-register the driver with RDBSS and remove the registration information from the internal RDBSS registration table.
old-location: ifsk\rxpunregisterminirdr.htm
tech.root: ifsk
ms.assetid: 84155e3f-8090-4b0d-a101-25ecd126bc37
ms.date: 04/16/2018
ms.keywords: RxpUnregisterMinirdr, RxpUnregisterMinirdr function [Installable File System Drivers], ifsk.rxpunregisterminirdr, mrx/RxpUnregisterMinirdr, rxref_3d8dd57c-4753-47c7-afda-efbd54882c74.xml
ms.topic: function
f1_keywords:
 - "mrx/RxpUnregisterMinirdr"
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
- RxpUnregisterMinirdr
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxpUnregisterMinirdr function


## -description


<b>RxpUnregisterMinirdr</b> is called by a network mini-redirector driver to de-register the driver with RDBSS and remove the registration information from the internal RDBSS registration table.


## -parameters




### -param RxDeviceObject [in]

A pointer to the RDBSS device object for this network redirector.


## -remarks



The <b>RxpUnregisterMinirdr</b> routine unregisters the driver with RDBSS and removes the registration information from the internal RDBSS registration table. If name tables were initialized, then these tables will be finalized for release. Any outstanding asynchronous requests to the network mini-redirector are spun down, and any worker threads associated with the redirector are spun down. <b>RxpUnregisterMinirdr</b> also tries to remove the device object from the system by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iodeletedevice">IoDeleteDevice</a>.

The <b>RxpUnregisterMinirdr </b>routine is usually called as a result of an FSCTL or IOCTL request from a user-mode application or service to unload the network mini-redirector, although this call could also be made from the network mini-redirector or as part of shutdown processing by the operating system or as a result of a failure in the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine. 

Note that the inline routine, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxstruc/nf-rxstruc-rxunregisterminirdr">RxUnregisterMinirdr</a>, is the preferred way to unregister a driver with RDBSS. The <b>RxUnregisterMinirdr</b> inline routine calls <b>RxpUnregisterMinirdr</b>, but then also decrements the object reference to the RDBSS device object so that this object can be released by the system. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iodeletedevice">IoDeleteDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nf-mrx-rxregisterminirdr">RxRegisterMinirdr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nf-mrx-rxstartminirdr">RxStartMiniRdr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mrx/nf-mrx-rxstopminirdr">RxStopMiniRdr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxstruc/nf-rxstruc-rxunregisterminirdr">RxUnregisterMinirdr</a>
 

 

