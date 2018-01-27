---
UID: NS:61883._CMP_MONITOR_PLUGS
title: _CMP_MONITOR_PLUGS
author: windows-driver-content
description: This structure is used to monitor plug access. The request allows a driver to monitor all access to local oPCR and iPCR plugs.
old-location: ieee\cmp_monitor_plugs.htm
old-project: IEEE
ms.assetid: D281BCBB-CDC6-442C-9A47-DF07D1BE1B28
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: 61883/CMP_MONITOR_PLUGS, *PCMP_MONITOR_PLUGS, IEEE.cmp_monitor_plugs, PCMP_MONITOR_PLUGS, CMP_MONITOR_PLUGS, 61883/PCMP_MONITOR_PLUGS, PCMP_MONITOR_PLUGS structure pointer [Buses], _CMP_MONITOR_PLUGS, CMP_MONITOR_PLUGS structure [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	61883.h
apiname: 
-	CMP_MONITOR_PLUGS
product: Windows
targetos: Windows
req.typenames: *PCMP_MONITOR_PLUGS, CMP_MONITOR_PLUGS
---

# _CMP_MONITOR_PLUGS structure


## -description


This structure is used to monitor plug access. The request allows a driver to monitor all access to local oPCR and iPCR plugs.


## -syntax


````
typedef struct _CMP_MONITOR_PLUGS {
  ULONG                Flags;
  PCMP_MONITOR_ROUTINE pfnNotify;
  PVOID                Context;
} CMP_MONITOR_PLUGS, *PCMP_MONITOR_PLUGS;
````


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


### -field Context

On input, a pointer to a caller-defined context for the function at <b>pfnNotify</b>.


##### - pfnNotify.MonitorInfo

On input, a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537050">CMP_MONITOR_INFO</a> structure containing the contents of the plug that was modified. 


## -remarks


If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20CMP_MONITOR_PLUGS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

