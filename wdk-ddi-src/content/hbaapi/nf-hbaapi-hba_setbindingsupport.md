---
UID: NF:hbaapi.HBA_SetBindingSupport
title: HBA_SetBindingSupport function
author: windows-driver-content
description: The HBA_SetBindingSupport routine enables the indicated set of capabilities on the adapter.
old-location: storage\hba_setbindingsupport.htm
tech.root: storage
ms.assetid: 2d4ac375-ede9-406e-bac0-9caa2273c91a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HBA_SetBindingSupport, HBA_SetBindingSupport routine [Storage Devices], fibreHBA_rtns_5adce4be-2d9d-4e53-ab21-3a15810153d7.xml, hbaapi/HBA_SetBindingSupport, storage.hba_setbindingsupport
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
-	HBA_SetBindingSupport
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_SetBindingSupport function


## -description


The <b>HBA_SetBindingSupport</b> routine enables the indicated set of capabilities on the adapter. 


## -parameters




### -param Handle [in]

Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the HBA on which the port referenced by <i>HbaPortWWN </i>is located. 


### -param HbaPortWWN [in]

Contains a 64-bit worldwide name (WWN) that uniquely identifies the port for which the binding capabilities specified by <i>Flags </i>are enabled. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification. 


### -param Flags [in]

Contains a bitwise OR of a set of flags that indicate the capabilities to enable on the port referenced by <i>HbaPortWWN</i>. For a description of the flags, see the corresponding values associated with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556046">HBA_BIND_TYPE</a> WMI property qualifier.


## -returns



The <b>HBA_SetBindingSupport</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_SetBindingSupport</b> returns one of the following values.

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
Returned if the binding capabilities were successfully enabled. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>
</td>
<td width="60%">
Returned if the HBA referenced by <i>handle</i> does not contain a port with a name that matches <i>HbaPortWWN</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Returned if the adapter referenced by <i>handle </i>does not support persistent bindings. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_INCAPABLE</b></dt>
</dl>
</td>
<td width="60%">
Returned if one or more of the flags specified by <i>Flags</i> corresponds to a capability not implemented for the port referenced by <i>HbaPortWWN</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the routine from enabling the specified capabilities. 

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

