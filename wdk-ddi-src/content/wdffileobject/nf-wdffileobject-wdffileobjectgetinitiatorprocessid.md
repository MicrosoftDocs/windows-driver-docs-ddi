---
UID: NF:wdffileobject.WdfFileObjectGetInitiatorProcessId
title: WdfFileObjectGetInitiatorProcessId function (wdffileobject.h)
description: The WdfFileObjectGetInitiatorProcessId function retrieves the initiator process ID that is associated with a specified framework file object.
old-location: wdf\wdffileobjectgetinitiatorprocessid.htm
tech.root: wdf
ms.assetid: 59E15EAA-4934-48D9-A9E3-7CDEEAE01985
ms.date: 02/26/2018
keywords: ["WdfFileObjectGetInitiatorProcessId function"]
ms.keywords: WdfFileObjectGetInitiatorProcessId, WdfFileObjectGetInitiatorProcessId function, wdf.wdffileobjectgetinitiatorprocessid, wdffileobject/WdfFileObjectGetInitiatorProcessId
f1_keywords:
 - "wdffileobject/WdfFileObjectGetInitiatorProcessId"
 - "WdfFileObjectGetInitiatorProcessId"
req.header: wdffileobject.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.21
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.lib
req.dll: WUDFx02000.dll
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- WUDFx02000.dll
api_name:
- WdfFileObjectGetInitiatorProcessId
targetos: Windows
req.typenames: 
---

# WdfFileObjectGetInitiatorProcessId function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfFileObjectGetInitiatorProcessId</b> function retrieves the initiator process ID that is associated with a specified framework file object.


## -parameters




### -param FileObject 
[in]
A handle to a framework file object.


## -returns



Returns the initiator process identifier associated with the file, if any exists. Otherwise, the function returns zero.




## -remarks



Starting in Windows 8, a system component may issue a create on behalf of an application. The driver can call <b>WdfFileObjectGetInitiatorProcessId</b> to determine which process the create operation is ultimately intended for.

<b>WdfFileObjectGetInitiatorProcessId</b> returns zero if no initiator process is associated with the create operation.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdffile3-getinitiatorprocessid">IWDFDevice3::GetInitiatorProcessId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetrequestorprocessid">WdfRequestGetRequestorProcessId</a>
 

 

