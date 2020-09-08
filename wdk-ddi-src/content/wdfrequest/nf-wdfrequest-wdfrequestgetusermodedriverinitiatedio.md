---
UID: NF:wdfrequest.WdfRequestGetUserModeDriverInitiatedIo
title: WdfRequestGetUserModeDriverInitiatedIo function (wdfrequest.h)
description: The WdfRequestGetUserModeDriverInitiatedIo method determines whether an I/O request is marked as initiated by a UMDF driver.
old-location: wdf\wdfrequestgetusermodeinitiatedio.htm
tech.root: wdf
ms.assetid: 3F2B060F-3818-4BBC-9BF7-7A82128274E0
ms.date: 02/26/2018
keywords: ["WdfRequestGetUserModeDriverInitiatedIo function"]
ms.keywords: WdfRequestGetUserModeDriverInitiatedIo, WdfRequestGetUserModeDriverInitiatedIo method, wdf.wdfrequestgetusermodeinitiatedio, wdfrequest/WdfRequestGetUserModeDriverInitiatedIo
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
req.dll: WUDFx02000.dll
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfRequestGetUserModeDriverInitiatedIo
 - wdfrequest/WdfRequestGetUserModeDriverInitiatedIo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - WUDFx02000.dll
api_name:
 - WdfRequestGetUserModeDriverInitiatedIo
---

# WdfRequestGetUserModeDriverInitiatedIo function


## -description

<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WdfRequestGetUserModeDriverInitiatedIo</b> method determines whether an I/O request is marked as initiated by a UMDF driver.

## -parameters

### -param Request 

[in]
A handle to a framework request object.

## -returns

The method returns <b>TRUE</b> if the request is marked as UMDF driver-initiated and <b>FALSE</b> if the request is not marked as UMDF driver-initiated.

## -remarks

 This method retrieves the value of the <b>IRP_UM_DRIVER_INITIATED_IO</b> flag in the <b>Flags</b> member of the WDM <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> structure corresponding to the I/O request.

For more information about using this flag, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsetusermodedriverinitiatedio">WdfRequestSetUserModeDriverInitiatedIo</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsetusermodedriverinitiatedio">WdfRequestSetUserModeDriverInitiatedIo</a>

