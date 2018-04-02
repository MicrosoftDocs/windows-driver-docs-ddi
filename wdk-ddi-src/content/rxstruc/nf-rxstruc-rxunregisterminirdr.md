---
UID: NF:rxstruc.RxUnregisterMinirdr
title: RxUnregisterMinirdr function
author: windows-driver-content
description: RxUnregisterMinirdr is an inline routine called by a network mini-redirector driver to de-register the driver with RDBSS and remove the registration information from the internal RDBSS registration table.
old-location: ifsk\rxunregisterminirdr.htm
old-project: ifsk
ms.assetid: 090e5fc5-a0cf-4df2-b9b9-abaf4833aef7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RxUnregisterMinirdr, RxUnregisterMinirdr routine [Installable File System Drivers], ifsk.rxunregisterminirdr, rxref_5c58f656-5d6a-46db-9c7e-f3331e48a66a.xml, rxstruc/RxUnregisterMinirdr
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxstruc.h
api_name:
-	RxUnregisterMinirdr
product:
- Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxUnregisterMinirdr function


## -description


<b>RxUnregisterMinirdr</b> is an inline routine called by a network mini-redirector driver to de-register the driver with RDBSS and remove the registration information from the internal RDBSS registration table.


## -parameters




### -param RxDeviceObject [in]

A pointer to the RDBSS device object for this network redirector.


## -returns



None




## -remarks



<b>RxUnregisterMinirdr</b> is an inline routine defined in <i>rxstruc.h</i> that de-registers the driver with RDBSS and removes the registration information from the internal RDBSS registration table. If name tables were initialized, then these tables will be finalized for release. Any outstanding asynchronous requests to the network mini-redirector are spun down, and any worker threads associated with the redirector are spun down. <b>RxUnregisterMinirdr</b> also tries to remove the device object from the system by calling <b>IoDeleteDevice</b>.

Typically, the <b>RxUnregisterMinirdr </b>routine is called as a result of an FSCTL or IOCTL request from a user-mode application or service to unload the network mini-redirector, although this call could also be made from the network mini-redirector or as part of shutdown processing by the operating system or as a result of a failure in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine.

Note that the inline routine, <b>RxUnregisterMinirdr</b>, is the preferred way to unregister a driver with RDBSS. The <b>RxUnregisterMinirdr</b> inline routine calls <b>RxpUnregisterMinirdr</b>, but then also decrements the object reference to the RDBSS device object so that this object can be released by the system. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549083">IoDeleteDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554693">RxRegisterMinirdr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554736">RxStartMiniRdr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554743">RxStopMiniRdr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554662">RxpUnregisterMinirdr</a>
 

 

