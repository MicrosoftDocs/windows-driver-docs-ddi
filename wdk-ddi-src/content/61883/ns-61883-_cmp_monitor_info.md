---
UID: NS:61883._CMP_MONITOR_INFO
title: _CMP_MONITOR_INFO
author: windows-driver-content
description: The CMP_MONITOR_INFO structure is used in conjunction with the Av61883_MonitorPlugs request to allow a driver to monitor access to local oPCR and iPCR plugs.
old-location: ieee\cmp_monitor_info.htm
old-project: IEEE
ms.assetid: 258bcd6f-0536-48d3-a06a-10277f8bef87
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _CMP_MONITOR_INFO, CMP_MONITOR_INFO, *PCMP_MONITOR_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 61883.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CMP_MONITOR_INFO
req.alt-loc: 61883.h
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
req.typenames: CMP_MONITOR_INFO, *PCMP_MONITOR_INFO
---

# _CMP_MONITOR_INFO structure



## -description
The CMP_MONITOR_INFO structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536987">Av61883_MonitorPlugs</a> request to allow a driver to monitor access to local oPCR and iPCR plugs.



## -syntax

````
typedef struct _CMP_MONITOR_INFO {
  ULONG  State;
  ULONG  PlugNum;
  ULONG  PlugType;
  AV_PCR Pcr;
  PVOID  Context;
} CMP_MONITOR_INFO, *PCMP_MONITOR_INFO;
````


## -struct-fields

### -field State

The current state of the plug.


### -field PlugNum

The number of the plug that was accessed.


### -field PlugType

The type of plug, either CMP_PlugOut or CMP_PlugIn.


### -field Pcr

The current contents of the plug.


### -field Context

Points to a caller-defined context that was registered with <a href="https://msdn.microsoft.com/library/windows/hardware/ff536987">Av61883_MonitorPlugs</a>.


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536987">Av61883_MonitorPlugs</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20CMP_MONITOR_INFO structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

