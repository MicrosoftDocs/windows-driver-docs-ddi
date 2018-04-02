---
UID: NF:hbaapi.HBA_GetBindingSupport
title: HBA_GetBindingSupport function
author: windows-driver-content
description: The HBA_GetBindingSupport routine retrieves the binding capabilities currently enabled for the specified port.
old-location: storage\hba_getbindingsupport.htm
old-project: storage
ms.assetid: 60542ed9-fbb0-48a3-bc97-ce3db7b4ae10
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HBA_GetBindingSupport, HBA_GetBindingSupport routine [Storage Devices], fibreHBA_rtns_98be4752-e595-4f33-b688-a373588c16f0.xml, hbaapi/HBA_GetBindingSupport, storage.hba_getbindingsupport
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
-	HBA_GetBindingSupport
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_GetBindingSupport function


## -description


The <b>HBA_GetBindingSupport</b> routine retrieves the binding capabilities currently enabled for the specified port.


## -parameters




### -param Handle [in]

Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the HBA on which the port is located. 


### -param HbaPortWWN [in]

Contains a 64-bit world-wide name (WWN) that uniquely identifies the local HBA port for which this routine retrieves persistent binding capabilities that are currently enabled. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -param Flags [out]

Contains a bitwise OR of flags associated with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556046">HBA_BIND_TYPE</a> WMI property qualifier that represent the persistent binding capabilities of the port that are currently enabled. 


## -returns



The <b>HBA_GetBindingSupport</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetBindingCapability</b> returns one of the following qualifiers.

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556046">HBA_BIND_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

