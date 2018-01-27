---
UID: NF:wdfrequest.WdfRequestGetUserModeDriverInitiatedIo
title: WdfRequestGetUserModeDriverInitiatedIo function
author: windows-driver-content
description: The WdfRequestGetUserModeDriverInitiatedIo method determines whether an I/O request is marked as initiated by a UMDF driver.
old-location: wdf\wdfrequestgetusermodeinitiatedio.htm
old-project: wdf
ms.assetid: 3F2B060F-3818-4BBC-9BF7-7A82128274E0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfrequest/WdfRequestGetUserModeDriverInitiatedIo, wdf.wdfrequestgetusermodeinitiatedio, WdfRequestGetUserModeDriverInitiatedIo, WdfRequestGetUserModeDriverInitiatedIo method
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
req.lib: WUDFx02000.lib
req.dll: WUDFx02000.dll; TBD
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	WUDFx02000.dll
apiname: 
-	WdfRequestGetUserModeDriverInitiatedIo
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestGetUserModeDriverInitiatedIo function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfRequestGetUserModeDriverInitiatedIo</b> method determines whether an I/O request is marked as initiated by a UMDF driver.


## -syntax


````
BOOLEAN WdfRequestGetUserModeDriverInitiatedIo(
  _In_ WDFREQUEST Request
);
````


## -parameters




### -param Request [in]

A handle to a framework request object.


## -returns


The method returns <b>TRUE</b> if the request is marked as UMDF driver-initiated and <b>FALSE</b> if the request is not marked as UMDF driver-initiated.



## -remarks


 This method retrieves the value of the <b>IRP_UM_DRIVER_INITIATED_IO</b> flag in the <b>Flags</b> member of the WDM <a href="..\wdm\ns-wdm-_irp.md">IRP</a> structure corresponding to the I/O request.

For more information about using this flag, see <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetusermodedriverinitiatedio.md">WdfRequestSetUserModeDriverInitiatedIo</a>.



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetusermodedriverinitiatedio.md">WdfRequestSetUserModeDriverInitiatedIo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestGetUserModeDriverInitiatedIo method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

