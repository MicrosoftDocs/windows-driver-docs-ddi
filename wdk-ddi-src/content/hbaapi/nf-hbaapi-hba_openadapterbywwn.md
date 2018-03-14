---
UID: NF:hbaapi.HBA_OpenAdapterByWWN
title: HBA_OpenAdapterByWWN function
author: windows-driver-content
description: The HBA_OpenAdapterByWWN routine opens the HBA that is associated with either a node or a port that has the indicated name.
old-location: storage\hba_openadapterbywwn.htm
old-project: storage
ms.assetid: 62492c9b-ace0-48be-ae8b-bb681dbca8b7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HBA_OpenAdapterByWWN, HBA_OpenAdapterByWWN routine [Storage Devices], fibreHBA_rtns_60fafeb4-de69-40e4-8942-907fe14fe8a4.xml, hbaapi/HBA_OpenAdapterByWWN, storage.hba_openadapterbywwn
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
-	HBA_OpenAdapterByWWN
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_OpenAdapterByWWN function


## -description


The <b>HBA_OpenAdapterByWWN</b> routine opens the HBA that is associated with either a node or a port that has the indicated name. 


## -syntax


````
HBA_STATUS HBA_API HBA_OpenAdapterByWWN(
  _Out_ HBA_HANDLE *HbaHandle,
  _In_  HBA_WWN    Wwn
);
````


## -parameters




### -param HbaHandle [out]

Contains, on output, a handle that identifies the HBA. 


### -param Wwn [in]

Contains a 64-bit worldwide name (WWN) that must either match the name of the node on which the HBA is located, or must match the name of a port on the HBA. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification. 


## -returns



The <b>HBA_OpenAdapterByWWN</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_OpenAdapterByWWN</b> returns one of the following qualifiers.

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
Returned if <b>HBA_OpenAdapterByWWN</b> successfully returns a valid handle. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>
</td>
<td width="60%">
Returned if there is no HBA that has a port name or node name that matches <i>Wwn</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_AMBIGUOUS_WWN</b></dt>
</dl>
</td>
<td width="60%">
Returned if multiple adapters have associated port or node names that match <i>Wwn</i>. This can occur if two or more adapters are associated with nodes of the same name. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the opening of the adapter. 

</td>
</tr>
</table>
 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



 

 


