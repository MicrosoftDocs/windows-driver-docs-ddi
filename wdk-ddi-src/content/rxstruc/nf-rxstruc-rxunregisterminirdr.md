---
UID: NF:rxstruc.RxUnregisterMinirdr
title: RxUnregisterMinirdr function
author: windows-driver-content
description: RxUnregisterMinirdr is an inline routine called by a network mini-redirector driver to de-register the driver with RDBSS and remove the registration information from the internal RDBSS registration table.
old-location: ifsk\rxunregisterminirdr.htm
old-project: ifsk
ms.assetid: 090e5fc5-a0cf-4df2-b9b9-abaf4833aef7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , M, R, RxUnregisterMinirdr, RxUnregisterMinirdr routine [Installable File System Drivers], U, d, e, g, i, ifsk.rxunregisterminirdr, n, r, rxref_5c58f656-5d6a-46db-9c7e-f3331e48a66a.xml, rxstruc/RxUnregisterMinirdr, s, t, x"
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rxstruc.h
apiname:
-	RxUnregisterMinirdr
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxUnregisterMinirdr function


## -description


<b>RxUnregisterMinirdr</b> is an inline routine called by a network mini-redirector driver to de-register the driver with RDBSS and remove the registration information from the internal RDBSS registration table.


## -syntax


````
VOID RxUnregisterMinirdr(
  _In_ PRDBSS_DEVICE_OBJECT RxDeviceObject
);
````


## -parameters




### -param RxDeviceObject [in]

A pointer to the RDBSS device object for this network redirector.


## -returns



None




## -remarks



<b>RxUnregisterMinirdr</b> is an inline routine defined in <i>rxstruc.h</i> that de-registers the driver with RDBSS and removes the registration information from the internal RDBSS registration table. If name tables were initialized, then these tables will be finalized for release. Any outstanding asynchronous requests to the network mini-redirector are spun down, and any worker threads associated with the redirector are spun down. <b>RxUnregisterMinirdr</b> also tries to remove the device object from the system by calling <b>IoDeleteDevice</b>.

Typically, the <b>RxUnregisterMinirdr </b>routine is called as a result of an FSCTL or IOCTL request from a user-mode application or service to unload the network mini-redirector, although this call could also be made from the network mini-redirector or as part of shutdown processing by the operating system or as a result of a failure in the <a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a> routine.

Note that the inline routine, <b>RxUnregisterMinirdr</b>, is the preferred way to unregister a driver with RDBSS. The <b>RxUnregisterMinirdr</b> inline routine calls <b>RxpUnregisterMinirdr</b>, but then also decrements the object reference to the RDBSS device object so that this object can be released by the system. 




## -see-also

<a href="..\wdm\nf-wdm-iodeletedevice.md">IoDeleteDevice</a>



<a href="..\mrx\nf-mrx-rxstopminirdr.md">RxStopMiniRdr</a>



<a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a>



<a href="..\mrx\nf-mrx-rxpunregisterminirdr.md">RxpUnregisterMinirdr</a>



<a href="..\mrx\nf-mrx-rxregisterminirdr.md">RxRegisterMinirdr</a>



<a href="..\mrx\nf-mrx-rxstartminirdr.md">RxStartMiniRdr</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxUnregisterMinirdr routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

