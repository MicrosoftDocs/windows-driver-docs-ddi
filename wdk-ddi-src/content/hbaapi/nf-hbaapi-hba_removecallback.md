---
UID: NF:hbaapi.HBA_RemoveCallback
title: HBA_RemoveCallback function
description: The HBA_RemoveCallback routine de-registers a callback routine.
old-location: storage\hba_removecallback.htm
tech.root: storage
ms.assetid: 9b97e93c-a375-4df7-9d2d-86f1ad72b62d
ms.date: 03/29/2018
ms.keywords: HBA_RemoveCallback, HBA_RemoveCallback routine [Storage Devices], fibreHBA_rtns_f0c88702-5544-4e66-ac3e-a5f8303bfb08.xml, hbaapi/HBA_RemoveCallback, storage.hba_removecallback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_RemoveCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_RemoveCallback function


## -description


The <b>HBA_RemoveCallback</b> routine de-registers a callback routine. 


## -parameters




### -param callbackHandle [in]

Contains an opaque handle specified with the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the callback routine to de-register. 


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

