---
UID: NF:wdfrequest.WdfRequestSetUserModeDriverInitiatedIo
title: WdfRequestSetUserModeDriverInitiatedIo function
description: The WdfRequestSetUserModeDriverInitiatedIo method indicates to kernel-mode drivers that sit below the UMDF driver in the same device stack that a particular request should be treated as though it came from a UMDF driver.
old-location: wdf\wdfrequestsetusermodedriverinitiatedio.htm
tech.root: wdf
ms.assetid: F477ABEA-5E29-4934-995C-D7FB1EF87A5B
ms.date: 02/26/2018
ms.keywords: WdfRequestSetUserModeDriverInitiatedIo, WdfRequestSetUserModeDriverInitiatedIo method, wdf.wdfrequestsetusermodedriverinitiatedio, wdfrequest/WdfRequestSetUserModeDriverInitiatedIo
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WUDFx02000.lib; WUDFx02000.dll
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	WUDFx02000.lib
-	WUDFx02000.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfRequestSetUserModeDriverInitiatedIo
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestSetUserModeDriverInitiatedIo function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WdfRequestSetUserModeDriverInitiatedIo</b> method indicates to kernel-mode drivers that sit below the UMDF driver in the same device stack that a particular request should be treated as though it came from a UMDF driver.


## -parameters




### -param Request [in]

A handle to a framework request object.


### -param IsUserModeDriverInitiated [in]

A Boolean value that, if <b>TRUE</b>, indicates that the request should be treated as though it was initiated by a UMDF driver. If <b>FALSE</b>, this parameter indicates that the request should be treated as though it came from an application.


## -returns



This method does not return a value.




## -remarks



If a UMDF driver calls this method with the <i>IsUserModeDriverInitiated</i> parameter set to <b>TRUE</b>, the framework sets the <b>IRP_UM_DRIVER_INITIATED_IO</b> flag in the <b>Flags</b> member of the WDM <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure before forwarding the request to kernel-mode drivers.

A kernel-mode driver that resides below the UMDF driver in the same device stack can check for this flag to determine if the request should be treated as though initiated by a UMDF driver.

This flag is not applicable to kernel-mode drivers that might receive a request from a UMDF driver via a file-handle I/O target or a Win32 I/O target.

A UMDF driver might set the <i>IsUserModeDriverInitiated</i> parameter to <b>TRUE</b> for a request that came from an application if the driver has validated the request.

Requests that the driver created on its own are already marked as having originated from a UMDF driver.




## -see-also




<a href="https://msdn.microsoft.com/3F2B060F-3818-4BBC-9BF7-7A82128274E0">WdfRequestGetUserModeDriverInitiatedIo</a>
 

 

