---
UID: NF:wdfrequest.WdfRequestRetrieveActivityId
title: WdfRequestRetrieveActivityId function
author: windows-driver-content
description: The WdfRequestRetrieveActivityId method retrieves the current activity identifier associated with an I/O request.
old-location: wdf\wdfrequestretrieveactivityid.htm
tech.root: wdf
ms.assetid: 6E38514E-75BD-4F98-AD12-FA4E31654C3E
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfRequestRetrieveActivityId, WdfRequestRetrieveActivityId method, wdf.wdfrequestretrieveactivityid, wdfrequest/WdfRequestRetrieveActivityId
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
req.dll: WUDFx02000.dll
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	WUDFx02000.dll
api_name:
-	WdfRequestRetrieveActivityId
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestRetrieveActivityId function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WdfRequestRetrieveActivityId</b> method retrieves the current activity identifier associated with an I/O request.


## -parameters




### -param Request [in]

A handle to a framework request object.


### -param ActivityId [out]

A pointer to a location to store the retrieved GUID.


## -returns



If the operation succeeds, <b>WdfRequestRetrieveActivityId</b> returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No activity ID is associated with the request.

</td>
</tr>
</table>
 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



Requests reflected from kernel mode have an activity identifier available only if the Kernel Trace provider is enabled or if the UMDF driver called <a href="https://msdn.microsoft.com/library/windows/hardware/dn265622">WdfRequestSetActivityId</a> after receiving the request. For more information about Event Tracing for Windows (ETW), see <a href="https://msdn.microsoft.com/3de69436-671b-46a2-8d92-4eb3af2a4233">Event Tracing</a>.

Requests initiated by the UMDF driver have an activity identifier available only if the UMDF driver previously called  <a href="https://msdn.microsoft.com/library/windows/hardware/dn265622">WdfRequestSetActivityId</a>.

The framework does not clear a request's activity identifier when the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>.

For more information about activity identifiers, see <a href="https://msdn.microsoft.com/2B70953F-5192-4654-9506-6A84373D20B4">Using Activity Identifiers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265622">WdfRequestSetActivityId</a>
 

 

