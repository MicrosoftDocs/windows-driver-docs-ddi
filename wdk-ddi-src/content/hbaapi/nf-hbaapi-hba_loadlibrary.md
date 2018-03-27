---
UID: NF:hbaapi.HBA_LoadLibrary
title: HBA_LoadLibrary function
author: windows-driver-content
description: The HBA_LoadLibrary routine loads and initializes the system-supplied fibre channel HBA API library.
old-location: storage\hba_loadlibrary.htm
old-project: storage
ms.assetid: f71be39c-4b0c-47fc-a9d5-dfe69d8b11f2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HBA_LoadLibrary, HBA_LoadLibrary routine [Storage Devices], fibreHBA_rtns_59c2bca3-3df2-4a3a-aa0b-90afcbdd26da.xml, hbaapi/HBA_LoadLibrary, storage.hba_loadlibrary
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_LoadLibrary
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_LoadLibrary function


## -description


The <b>HBA_LoadLibrary</b> routine loads and initializes the system-supplied fibre channel HBA API library. 


## -parameters






## -returns



The <b>HBA_LoadLibrary</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_LoadLibrary</b> returns one of the following qualifiers.

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
Returned if the library loaded properly. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ALREADY_LOADED</b></dt>
</dl>
</td>
<td width="60%">
Returned if the library is already loaded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_INCOMPATIBLE</b></dt>
</dl>
</td>
<td width="60%">
Returned if <b>HBA_LoadLibrary</b> discovered incompatibilities between the library and the associated HBA drivers. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the library from loading. 

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_LoadLibrary routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

