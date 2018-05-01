---
UID: NF:hbaapi.HBA_LoadLibrary
title: HBA_LoadLibrary function
author: windows-driver-content
description: The HBA_LoadLibrary routine loads and initializes the system-supplied fibre channel HBA API library.
old-location: storage\hba_loadlibrary.htm
old-project: storage
ms.assetid: f71be39c-4b0c-47fc-a9d5-dfe69d8b11f2
ms.author: windowsdriverdev
ms.date: 3/29/2018
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
req.typenames: 
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
 

 

