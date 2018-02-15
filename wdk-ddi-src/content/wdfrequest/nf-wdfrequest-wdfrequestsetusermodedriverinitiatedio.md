---
UID: NF:wdfrequest.WdfRequestSetUserModeDriverInitiatedIo
title: WdfRequestSetUserModeDriverInitiatedIo function
author: windows-driver-content
description: The WdfRequestSetUserModeDriverInitiatedIo method indicates to kernel-mode drivers that sit below the UMDF driver in the same device stack that a particular request should be treated as though it came from a UMDF driver.
old-location: wdf\wdfrequestsetusermodedriverinitiatedio.htm
old-project: wdf
ms.assetid: F477ABEA-5E29-4934-995C-D7FB1EF87A5B
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFREQUESTSETUSERMODEDRIVERINITIATEDIO, WdfRequestSetUserModeDriverInitiatedIo method, wdfrequest/WdfRequestSetUserModeDriverInitiatedIo, wdf.wdfrequestsetusermodedriverinitiatedio, WdfRequestSetUserModeDriverInitiatedIo
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	WUDFx02000.lib
-	WUDFx02000.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfRequestSetUserModeDriverInitiatedIo
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestSetUserModeDriverInitiatedIo function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfRequestSetUserModeDriverInitiatedIo</b> method indicates to kernel-mode drivers that sit below the UMDF driver in the same device stack that a particular request should be treated as though it came from a UMDF driver.


## -syntax


````
void WdfRequestSetUserModeDriverInitiatedIo(
  _In_ WDFREQUEST Request,
  _In_ BOOLEAN    IsUserModeDriverInitiated
);
````


## -parameters




### -param Request [in]

A handle to a framework request object.


### -param IsUserModeDriverInitiated [in]

A Boolean value that, if <b>TRUE</b>, indicates that the request should be treated as though it was initiated by a UMDF driver. If <b>FALSE</b>, this parameter indicates that the request should be treated as though it came from an application.


## -returns



This method does not return a value.




## -remarks



If a UMDF driver calls this method with the <i>IsUserModeDriverInitiated</i> parameter set to <b>TRUE</b>, the framework sets the <b>IRP_UM_DRIVER_INITIATED_IO</b> flag in the <b>Flags</b> member of the WDM <a href="..\wdm\ns-wdm-_irp.md">IRP</a> structure before forwarding the request to kernel-mode drivers.

A kernel-mode driver that resides below the UMDF driver in the same device stack can check for this flag to determine if the request should be treated as though initiated by a UMDF driver.

This flag is not applicable to kernel-mode drivers that might receive a request from a UMDF driver via a file-handle I/O target or a Win32 I/O target.

A UMDF driver might set the <i>IsUserModeDriverInitiated</i> parameter to <b>TRUE</b> for a request that came from an application if the driver has validated the request.

Requests that the driver created on its own are already marked as having originated from a UMDF driver.




## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetusermodedriverinitiatedio.md">WdfRequestGetUserModeDriverInitiatedIo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestSetUserModeDriverInitiatedIo method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

