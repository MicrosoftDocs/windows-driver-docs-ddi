---
UID: NF:mrx.RxpUnregisterMinirdr
title: RxpUnregisterMinirdr function
author: windows-driver-content
description: RxpUnregisterMinirdr is called by a network mini-redirector driver to de-register the driver with RDBSS and remove the registration information from the internal RDBSS registration table.
old-location: ifsk\rxpunregisterminirdr.htm
tech.root: ifsk
ms.assetid: 84155e3f-8090-4b0d-a101-25ecd126bc37
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RxpUnregisterMinirdr, RxpUnregisterMinirdr function [Installable File System Drivers], ifsk.rxpunregisterminirdr, mrx/RxpUnregisterMinirdr, rxref_3d8dd57c-4753-47c7-afda-efbd54882c74.xml
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
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mrx.h
api_name:
-	RxpUnregisterMinirdr
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


## -returns



None




## -remarks



The <b>RxpUnregisterMinirdr</b> routine unregisters the driver with RDBSS and removes the registration information from the internal RDBSS registration table. If name tables were initialized, then these tables will be finalized for release. Any outstanding asynchronous requests to the network mini-redirector are spun down, and any worker threads associated with the redirector are spun down. <b>RxpUnregisterMinirdr</b> also tries to remove the device object from the system by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549083">IoDeleteDevice</a>.

The <b>RxpUnregisterMinirdr </b>routine is usually called as a result of an FSCTL or IOCTL request from a user-mode application or service to unload the network mini-redirector, although this call could also be made from the network mini-redirector or as part of shutdown processing by the operating system or as a result of a failure in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine. 

Note that the inline routine, <a href="https://msdn.microsoft.com/library/windows/hardware/ff554744">RxUnregisterMinirdr</a>, is the preferred way to unregister a driver with RDBSS. The <b>RxUnregisterMinirdr</b> inline routine calls <b>RxpUnregisterMinirdr</b>, but then also decrements the object reference to the RDBSS device object so that this object can be released by the system. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549083">IoDeleteDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554693">RxRegisterMinirdr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554736">RxStartMiniRdr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554743">RxStopMiniRdr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554744">RxUnregisterMinirdr</a>
 

 

