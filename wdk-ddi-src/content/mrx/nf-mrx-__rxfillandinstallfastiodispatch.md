---
UID: NF:mrx.__RxFillAndInstallFastIoDispatch
title: __RxFillAndInstallFastIoDispatch function (mrx.h)
description: RxFillAndInstallFastIoDispatch fills out a fast I/O dispatch vector to be identical with the normal dispatch I/O vector and installs it into the driver object associated with the device object passed.
old-location: ifsk\__rxfillandinstallfastiodispatch.htm
tech.root: ifsk
ms.assetid: 4619a1aa-0c91-4b77-abbf-077f28437e0f
ms.date: 04/16/2018
ms.keywords: "__RxFillAndInstallFastIoDispatch, __RxFillAndInstallFastIoDispatch function [Installable File System Drivers], ifsk.__rxfillandinstallfastiodispatch, mrx/__RxFillAndInstallFastIoDispatch, rxref_5898351a-a474-44bb-8ba0-3d2edf81d073.xml"
ms.topic: function
f1_keywords:
 - "mrx/__RxFillAndInstallFastIoDispatch"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- mrx.h
api_name:
- __RxFillAndInstallFastIoDispatch
product:
- Windows
targetos: Windows
req.typenames: 
---

# __RxFillAndInstallFastIoDispatch function


## -description


<b>RxFillAndInstallFastIoDispatch</b> fills out a fast I/O dispatch vector to be identical with the normal dispatch I/O vector and installs it into the driver object associated with the device object passed.


## -parameters




### -param RxDeviceObject [in]

A pointer to the RDBSS device object for this network redirector.


### -param FastIoDispatch [in, out]

A pointer to the fast I/O dispatch table to fill in and use.


### -param FastIoDispatchSize [in]

The size, in bytes, of the fast I/O dispatch table passed.


## -returns



None




## -remarks



The <b>__RxFillAndInstallFastIoDispatch</b> routine is implemented differently for monolithic and non-monolithic drivers network mini-redirector. 

For non-monolithic network mini-redirector drivers, such as the Microsoft SMB redirector that links to rdbss.sys dynamically, <b>__RxFillAndInstallFastIoDispatch</b> is a convenience routine that copies the normal dispatch I/O vector table routines to the fast I/O dispatch vector table. This routine would normally be used by a non-monolithic network mini-redirector to fill out the fast I/O dispatch table before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrx/nf-mrx-rxregisterminirdr">RxRegisterMiniRdr</a>. This routine uses the minimum of the <i>FastIoDispatchSize</i> parameter and the size of the FAST_IO_DISPATCH structure defined in ntifs.h to determine the number of bytes to copy.

For monolithic network mini-redirectors built by developers, the <b>__RxFillAndInstallFastIoDispatch</b> routine does nothing.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrx/nf-mrx-rxregisterminirdr">RxRegisterMinirdr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrx/nf-mrx-rxsetdomainformailslotbroadcast">RxSetDomainForMailslotBroadcast</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrx/nf-mrx-rxstartminirdr">RxStartMiniRdr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mrx/nf-mrx-rxstopminirdr">RxStopMiniRdr</a>
 

 

