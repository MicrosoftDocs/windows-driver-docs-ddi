---
UID: NS:61883._CMP_MONITOR_INFO
title: "_CMP_MONITOR_INFO" (61883.h)
description: The CMP_MONITOR_INFO structure is used in conjunction with the Av61883_MonitorPlugs request to allow a driver to monitor access to local oPCR and iPCR plugs.
old-location: ieee\cmp_monitor_info.htm
tech.root: IEEE
ms.assetid: 258bcd6f-0536-48d3-a06a-10277f8bef87
ms.date: 02/15/2018
ms.keywords: "*PCMP_MONITOR_INFO, 61883/CMP_MONITOR_INFO, 61883/PCMP_MONITOR_INFO, 61883_structures_0064b5eb-7b9a-4f96-9e56-f3190d2fd7a3.xml, CMP_MONITOR_INFO, CMP_MONITOR_INFO structure [Buses], IEEE.cmp_monitor_info, PCMP_MONITOR_INFO, PCMP_MONITOR_INFO structure pointer [Buses], _CMP_MONITOR_INFO"
ms.topic: struct
req.header: 61883.h
req.include-header: 61883.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	61883.h
api_name:
-	CMP_MONITOR_INFO
product:
- Windows
targetos: Windows
req.typenames: CMP_MONITOR_INFO, *PCMP_MONITOR_INFO
---

# _CMP_MONITOR_INFO structure


## -description


The CMP_MONITOR_INFO structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536987">Av61883_MonitorPlugs</a> request to allow a driver to monitor access to local oPCR and iPCR plugs.


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


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536987">Av61883_MonitorPlugs</a>
 

 

