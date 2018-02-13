---
UID: NF:hbaapi.HBA_RemoveCallback
title: HBA_RemoveCallback function
author: windows-driver-content
description: The HBA_RemoveCallback routine de-registers a callback routine.
old-location: storage\hba_removecallback.htm
old-project: storage
ms.assetid: 9b97e93c-a375-4df7-9d2d-86f1ad72b62d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: fibreHBA_rtns_f0c88702-5544-4e66-ac3e-a5f8303bfb08.xml, storage.hba_removecallback, hbaapi/HBA_RemoveCallback, HBA_RemoveCallback, HBA_RemoveCallback routine [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hbaapi.dll
apiname:
-	HBA_RemoveCallback
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_RemoveCallback function


## -description


The <b>HBA_RemoveCallback</b> routine de-registers a callback routine. 


## -syntax


````
HBA_STATUS HBA_API HBA_RemoveCallback(
  _In_ HBA_CALLBACKHANDLE callbackHandle
);
````


## -parameters




### -param callbackHandle [in]

Contains an opaque handle specified with the call to <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the callback routine to de-register. 


## -returns



The <b>HBA_RemoveCallback</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_RemoveCallback</b> returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>
</td>
<td width="60%">
Returned if the callback routine was successfully de-registered. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the de-registration of the callback routine. 

</td>
</tr>
</table>
 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_RemoveCallback routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

