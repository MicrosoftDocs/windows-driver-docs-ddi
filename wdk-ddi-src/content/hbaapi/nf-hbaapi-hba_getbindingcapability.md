---
UID: NF:hbaapi.HBA_GetBindingCapability
title: HBA_GetBindingCapability function
author: windows-driver-content
description: The HBA_GetBindingCapability routine retrieves the binding capabilities of the indicated port.
old-location: storage\hba_getbindingcapability.htm
old-project: storage
ms.assetid: c4ac992a-7ef2-47b6-88d1-54b47b4a0af4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HBA_GetBindingCapability, HBA_GetBindingCapability routine [Storage Devices], fibreHBA_rtns_05b57109-c484-4faf-afaa-e5e833f47ee1.xml, hbaapi/HBA_GetBindingCapability, storage.hba_getbindingcapability
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
-	HBA_GetBindingCapability
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_GetBindingCapability function


## -description


The <b>HBA_GetBindingCapability</b> routine retrieves the binding capabilities of the indicated port. 


## -syntax


````
HBA_STATUS HBA_API HBA_GetBindingCapability(
  _In_  HBA_HANDLE          Handle,
  _In_  HBA_WWN             HbaPortWWN,
  _Out_ HBA_BIND_CAPABILITY *Flags
);
````


## -parameters




### -param Handle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA on which the port is located. 


### -param HbaPortWWN [in]

Contains a 64-bit worldwide name (WWN) that uniquely identifies the local HBA port whose persistent binding capabilities will be retrieved. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -param Flags [out]

Contains a bitwise OR of flags associated with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556046">HBA_BIND_TYPE</a> WMI property qualifier that represent the persistent binding capabilities of the port. 


## -returns



The <b>HBA_GetBindingCapability</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetBindingCapability</b> returns one of the following qualifiers.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>
</td>
<td width="60%">
Returned if the adapter does not contain a port with the name <i>HbaPortWWN</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Returned if the adapter does not support persistent bindings. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the retrieval of the port attributes.

</td>
</tr>
</table>
 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556046">HBA_BIND_TYPE</a>



 

 


