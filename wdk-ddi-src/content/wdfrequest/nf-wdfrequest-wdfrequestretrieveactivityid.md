---
UID: NF:wdfrequest.WdfRequestRetrieveActivityId
title: WdfRequestRetrieveActivityId function
author: windows-driver-content
description: The WdfRequestRetrieveActivityId method retrieves the current activity identifier associated with an I/O request.
old-location: wdf\wdfrequestretrieveactivityid.htm
old-project: wdf
ms.assetid: 6E38514E-75BD-4F98-AD12-FA4E31654C3E
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFREQUESTRETRIEVEACTIVITYID, wdfrequest/WdfRequestRetrieveActivityId, WdfRequestRetrieveActivityId, wdf.wdfrequestretrieveactivityid, WdfRequestRetrieveActivityId method
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
-	WdfRequestRetrieveActivityId
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestRetrieveActivityId function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfRequestRetrieveActivityId</b> method retrieves the current activity identifier associated with an I/O request.


## -syntax


````
NTSTATUS WdfRequestRetrieveActivityId(
  _In_  WDFREQUEST Request,
  _Out_ LPGUID     ActivityId
);
````


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


Requests reflected from kernel mode have an activity identifier available only if the Kernel Trace provider is enabled or if the UMDF driver called <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetactivityid.md">WdfRequestSetActivityId</a> after receiving the request. For more information about Event Tracing for Windows (ETW), see <a href="https://msdn.microsoft.com/3de69436-671b-46a2-8d92-4eb3af2a4233">Event Tracing</a>.

Requests initiated by the UMDF driver have an activity identifier available only if the UMDF driver previously called  <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetactivityid.md">WdfRequestSetActivityId</a>.

The framework does not clear a request's activity identifier when the driver calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>.

For more information about activity identifiers, see <a href="https://msdn.microsoft.com/2B70953F-5192-4654-9506-6A84373D20B4">Using Activity Identifiers</a>.



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsetactivityid.md">WdfRequestSetActivityId</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestRetrieveActivityId method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

