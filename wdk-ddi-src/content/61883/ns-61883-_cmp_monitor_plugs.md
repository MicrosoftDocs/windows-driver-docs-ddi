---
UID: NS:61883._CMP_MONITOR_PLUGS
title: _CMP_MONITOR_PLUGS (61883.h)
description: This structure is used to monitor plug access. The request allows a driver to monitor all access to local oPCR and iPCR plugs.
old-location: ieee\cmp_monitor_plugs.htm
tech.root: IEEE
ms.assetid: D281BCBB-CDC6-442C-9A47-DF07D1BE1B28
ms.date: 02/15/2018
keywords: ["CMP_MONITOR_PLUGS structure"]
ms.keywords: "*PCMP_MONITOR_PLUGS, 61883/CMP_MONITOR_PLUGS, 61883/PCMP_MONITOR_PLUGS, CMP_MONITOR_PLUGS, CMP_MONITOR_PLUGS structure [Buses], IEEE.cmp_monitor_plugs, PCMP_MONITOR_PLUGS, PCMP_MONITOR_PLUGS structure pointer [Buses], _CMP_MONITOR_PLUGS"
f1_keywords:
 - "61883/CMP_MONITOR_PLUGS"
 - "CMP_MONITOR_PLUGS"
req.header: 61883.h
req.include-header: 
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- 61883.h
api_name:
- CMP_MONITOR_PLUGS
targetos: Windows
req.typenames: CMP_MONITOR_PLUGS, *PCMP_MONITOR_PLUGS
---

# _CMP_MONITOR_PLUGS structure


## -description


This structure is used to monitor plug access. The request allows a driver to monitor all access to local oPCR and iPCR plugs.


## -struct-fields




### -field Flags

On input, the caller sets this member to REGISTER_MONITOR_PLUG_NOTIFY to register to monitor all local plug access. This member can also be set to DEREGISTER_MONITOR_PLUG_NOTIFY to stop monitoring local plug access.


### -field pfnNotify

On input, aointer to a caller-supplied function to be called by the protocol driver when a local plug is accessed. 

This function uses the following prototype: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef void
(*PCMP_MONITOR_ROUTINE) (
  IN PCMP_MONITOR_INFO  MonitorInfo
  );</pre>
</td>
</tr>
</table></span></div>




#### MonitorInfo

On input, a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_cmp_monitor_info">CMP_MONITOR_INFO</a> structure containing the contents of the plug that was modified. 


### -field Context

On input, a pointer to a caller-defined context for the function at <b>pfnNotify</b>.


## -remarks



If successful, the IEC-61883 protocol driver sets <b>Irp->IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp->IoStatus.Status </b>to STATUS_INVALID_PARAMETER.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_av_61883_request">AV_61883_REQUEST</a>
 

 

